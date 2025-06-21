# User_Panel
May be a user interface panel for visualisating and agregating images from camera inspections.

# 📸 Vizualizační systém pro kamerové kontroly

Tento projekt je webová aplikace pro přehledné a síťově dostupné zobrazení výsledků z vícero kamerových kontrol v průmyslovém prostředí. Každý kontrolovaný objekt je vyhodnocen na základě snímků z více kamer a výsledky jsou přehledně zobrazeny na interaktivní mapě objektu.

---

## 🎯 Hlavní cíle

- 📁 Automatické načítání vyhodnocených snímků z adresářové struktury
- 🔗 Spárování snímků dle ID kontrolovaného objektu
- 🧠 Vizualizace výsledků jako mapa nebo 3D nákres s barevnými indikátory
- 🌐 Webová aplikace dostupná z více zařízení v síti
- 🗃️ Možnost doprovodných metadat (JSON/CSV) ke každému objektu

---

## ⚙️ Architektura systému

Tato aplikace je rozdělena do dvou hlavních částí:

### 🟦 Backend (FastAPI)
- Sleduje soubory se snímky a metadata
- Zpracovává adresářovou strukturu a vytváří datové sady
- Poskytuje REST API pro frontend:
  - `/api/objects` – seznam všech vyhodnocených objektů
  - `/api/object/{id}` – detailní výsledky konkrétního objektu
  - `/api/image/{id}/{camera}` – náhled konkrétního snímku
  - `/api/map/{id}` – předpřipravený obrázek mapy (nebo SVG renderer)

### 🟩 Frontend (React)
- Zobrazuje přehled kontrolovaných objektů
- Zobrazuje interaktivní „mapu“ s vyhodnocením z jednotlivých kamer
- Umožňuje filtrování, hledání a detailní zobrazení výsledků
- Postaveno na komponentách s možností budoucího rozšíření

---

## 🧰 Technologie

| Komponenta | Technologie |
|-----------|-------------|
| Backend   | Python, FastAPI, Uvicorn, Watchdog |
| Frontend  | React.js, TailwindCSS / MUI, Axios |
| Build/deploy | Docker (volitelně), GitHub Actions (plánováno) |
| Verze     | Python 3.11+, Node.js 18+ |

---

## 📁 Struktura repozitáře


---

## 📌 Plán vývoje (milestones)

### ✅ Fáze 1 – MVP (minimum viable product)
- [x] Vytvoření základního FastAPI serveru
- [x] Endpoint `/api/objects`
- [ ] Frontend: přehled ID a jejich stavů (OK/NOK)
- [ ] Generování základní "mapy" kontrolního objektu

### ⏭️ Fáze 2 – Propojení snímků a JSON
- [ ] Sjednocení struktury dat pro různé kamery
- [ ] Vizualizace kontrol na 2D modelu pomocí SVG

### ⏭️ Fáze 3 – Pokročilé funkce
- [ ] Upload JSON/snímku přes webové rozhraní (volitelně)
- [ ] Export reportu (PDF nebo CSV)
- [ ] Autentizace uživatelů
- [ ] Režim operátora vs administrátora

---

## 🧠 Doporučení pro rozvoj

- Použít GitHub Issues pro sledování úkolů a plánů
- Nastavit CI/CD (GitHub Actions) pro automatické testy
- Přidat Docker kontejner pro snadné nasazení
- Rozšířit dokumentaci (`/docs`) o API specifikaci (OpenAPI / Swagger)
- Zavést jednotkové testy backendu pomocí `pytest`

---

## 📌 Licence

Projekt je aktuálně neveřejný / vývojový. Licence bude upřesněna později.

---

## 👨‍💻 Autor

Pavel Joura / [GitHub profile link]

