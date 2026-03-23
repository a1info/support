# Optima Prevent API Documentation

## Introduction

Optima Prevent offers a RESTful API (v1) for integration with mobile applications and external systems. The API enables user authentication, reading data via QR codes (ROA), and recording field data (work equipment inspections, e-tests, HRM time tracking).

All API calls communicate in `application/json` format and require authentication with Sanctum tokens sent in the request header:

```
Authorization: Bearer <token>
```

---

## 1. Authentication

### Main User Login (Inspector / Administrator)

Used to access the main modules (equipment inspections, HRM terminal).

**Request**

```http
POST /api/mobile/v1/login
Content-Type: application/json
```

```json
{
  "email": "admin@example.com",
  "password": "yourpassword"
}
```

**Response (200 OK)**

```json
{
  "token": "1|abc123def456ghi789...",
  "user": {
    "id": 1,
    "name": "Janez",
    "email": "admin@example.com"
  }
}
```

---

### Employee Login (E-Test)

Intended solely for taking e-tests with a special study access.

**Request**

```http
POST /api/mobile/v1/etest/login
Content-Type: application/json
```

```json
{
  "username": "janez_novak",
  "password": "etest_password"
}
```

**Response (200 OK)**

Returns a specific token used only for E-Test endpoints.

---

## 2. HRM Terminal (Time Tracking - NFC)

Records an employee’s clock-in or clock-out by reading an NFC chip/card. This call uses the main (admin) authentication and operates in kiosk mode.

**Request**

```http
POST /api/mobile/v1/hrm/attendance
Authorization: Bearer <main_token>
Content-Type: application/json
```

```json
{
  "salt": "04ef4abc83b280"
}
```

**Response (200 / 201 OK)**

```json
{
  "employee_name": "Janez Novak",
  "action": "in",
  "timestamp": "23. 03. 2026 07:32"
}
```

**Note:** `action` can be `"in"` or `"out"`.

---

## 3. Work Equipment (Device Checks)

### Read Equipment (QR Scan)

Retrieves equipment card information and a list of dynamic checkpoints ready for a new inspection. Supports direct references (`shdev`) and blank labels (`shblk`).

**Request**

```http
GET /api/mobile/v1/devices/qr/{salt}?type={shblk|shdev}
Authorization: Bearer <main_token>
```

**Response**

Returns a JSON structure containing:
- `device` (details)
- `latest_check` (status of the last inspection)
- `check_templates` (array of dynamic OTV/VZD matrix tests)

---

### Create a New Equipment Inspection

Records an inspection along with geolocation.

**Request**

```http
POST /api/mobile/v1/devices/{device_id}/checks
Authorization: Bearer <main_token>
Content-Type: application/json
```

```json
{
  "date_test": "2026-03-23",
  "ind_pass": true,
  "mnt_valid": 12,
  "location": "Warehouse 2",
  "descr": "Annual inspection successfully completed.",
  "geo_fi": 46.05694,
  "geo_lam": 14.50575,
  "checks": [
    { "custchktype_id": 1, "ind_pass": true },
    { "custchktype_id": 2, "ind_pass": false }
  ]
}
```

---

## 4. Fire Extinguishers (VPP Extinguishers)

### Read Fire Extinguisher (QR Scan)

**Request**

```http
GET /api/mobile/v1/extinguishers/qr/{salt}
Authorization: Bearer <main_token>
```

---

### Create a Fire Extinguisher Inspection

**Request**

```http
POST /api/mobile/v1/extinguishers/{extinguisher_id}/checks
Authorization: Bearer <main_token>
Content-Type: application/json
```

```json
{
  "inspectiontype_id": 1,
  "date_test": "2026-03-23",
  "mnt_valid": 12,
  "ind_pass": true,
  "geo_fi": 46.05694,
  "geo_lam": 14.50575
}
```

---

## 5. Employees (ROA Records)

Retrieves an employee’s personal protective equipment, medical certificates, and training certificates when scanning a QR code.

**Request**

```http
GET /api/mobile/v1/employees/qr/{salt}
Authorization: Bearer <main_token>
```

---

## 6. E-Test (Remote Testing)

### Retrieve Questions

Loads test data, video/pdf material, and generates a new solving log (`etestlog_id`).

**Request**

```http
GET /api/mobile/v1/etest/questions
Authorization: Bearer <etest_token>
```

---

### Submit Test Results

Records the user’s selected answers, calculates points and pass/fail status, and generates a certificate.

**Request**

```http
POST /api/mobile/v1/etest/submit
Authorization: Bearer <etest_token>
Content-Type: application/json
```

```json
{
  "etestlog_id": 9582,
  "answ": {
    "101": "a",
    "102": "c",
    "105": "b"
  }
}
```

**Response**

```json
{
  "passed": true,
  "points": 18,
  "max_points": 20,
  "message": "You have successfully passed the knowledge test."
}
```
