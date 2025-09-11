# Mediji in resursi za dokumentacijo

Mapa `media/` vsebuje vse slike, ikone in druge medijske vsebine za dokumentacijo Optima Prevent.

## 📁 Struktura map

### `/logos/`
Logotipi aplikacije in podjetja:
- `op-logo.png` - Osnovni logo Optima Prevent
- `op-logo-blue.png` - Modri logo
- `op-logo-grey.png` - Sivi logo

### `/icons/`
Ikone in majhne grafike:
- `op-favicon.png` - Favicon aplikacije
- `icon-chk-*.png` - Ikone za potrditvene okenčke
- `tbl-*.png` - Ikone za tabele

### `/screenshots/`
Posnetki zaslonov aplikacije:
- Nadzorna plošča
- Moduli aplikacije  
- Uporabniški vmesnik
- Namestitve in konfiguracije

### `/modules/`
Specifične slike za posamezne module:

#### `/modules/etest/`
- Vmesnik za teste
- Rezultati testiranj
- Statistike

#### `/modules/rassl/`
- Risk assessment vmesnik
- Ocene tveganj
- Poročila

#### `/modules/cust/`
- Upravljanje strank
- Profili strank
- Komunikacija

#### `/modules/roa/`
- Road assessment
- Prometne analize
- Varnostni ukrepi

#### `/modules/hrm/`
- HR upravljanje
- Zaposleni
- Usposabljanja

#### `/modules/crm/`
- CRM funkcionalnosti
- Priložnosti
- Analitika

## 🖼️ Navodila za slike

### Format slik
- **Posnetki zaslonov**: PNG format, maksimalno 1920x1080
- **Logotipi**: PNG z prosojnostjo
- **Ikone**: PNG ali SVG, 16x16, 32x32, 48x48

### Konvencije poimenovanja
```
screenshot_module_function_date.png
icon_type_variant_size.png  
logo_variant_size.png
```

### Optimizacija
Vse slike naj bodo optimizirane za splet:
- Kompresija brez izgube kvalitete
- Primerna ločljivost za prikaz
- Alt teksty v markdown dokumentih

## 📝 Uporaba v dokumentaciji

### Markdown sintaksa
```markdown
![Opis slike](media/screenshots/dashboard.png)
![Logo](media/logos/op-logo.png)
![Ikona](media/icons/op-favicon.png)
```

### Relativne poti
Vedno uporabljajte relativne poti glede na lokacijo markdown datoteke:
```markdown
# Z docs/ ravni:
![Slika](media/screenshots/example.png)

# Z docs/podpora/ ravni:
![Slika](../media/screenshots/example.png)
```

## 🔄 Vzdrževanje

### Dodajanje novih slik
1. Optimizirajte sliko za splet
2. Uporabite ustrezno konvencijo poimenovanja
3. Dodajte v ustrezno mapo
4. Posodobite dokumentacijo
5. Testirajte vse povezave

### Odstranjevanje slik
1. Preverite ali se slika uporablja v dokumentaciji
2. Poiščite vse reference v markdown datotekah
3. Odstranite ali nadomestite z novo sliko
4. Testirajte vse povezave

---

*Optimira Prevent © 2024 a1-info d.o.o., Slovenija*