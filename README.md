# 🌍 World Explorer — Frontend Zadatak (Junior Level)

## Live Demo: <br /> https://lazarmilovanovic.github.io/WorldExplorer/

## 📌 Opis zadatka

Cilj zadatka je da napraviš **responsivnu single-page aplikaciju** koja prikazuje države sveta koristeći **REST Countries API**.  
Aplikacija mora da bude rađena u **čistom HTML-u, CSS-u i JavaScript-u**.

Korisnik treba da može da pretražuje, filtrira, sortira, lista države i vidi detalje o svakoj državi.

---

## 🔗 API

Koristi se REST Countries API:

```text
https://restcountries.com/
Pogledaj dokumentaciju i istraži
```

Za svaku državu potrebno je prikazati makar ove podatke (može i više):

- `name.common`
- `name.official`
- `region`
- `subregion`
- `capital`
- `population`
- `flags.png` / `flags.svg`
- `languages`
- `currencies`
- `borders`

---

## 🎨 UI Dizajn (ASCII mockup)

Ovo je vizuelni prikaz željenog UI-ja za desktop, mobilni i modal prikaz.

### 🖥 Desktop layout

```text
┌────────────────────────────────────────────────────────────┐
│ 🌍 World Explorer                           ○ Dark/Light   │
├────────────────────────────────────────────────────────────┤

│ Search: [ Search countries…________ ]  Region: [ Europe▼ ] │
│ Sort by: [ Name (A–Z) ▼ ]                                   │

├────────────────────────────────────────────────────────────┤
│  Total countries: 250                     Status: Loaded    │
├────────────────────────────────────────────────────────────┤

│ ┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐ │
│ │ [ FLAG ]        │ │ [ FLAG ]        │ │ [ FLAG ]        │ │
│ │ Serbia          │ │ Germany         │ │ Japan           │ │
│ │ Region: Europe  │ │ Region: Europe  │ │ Region: Asia    │ │
│ │ Capital: BG     │ │ Capital: Berlin │ │ Capital: Tokyo  │ │
│ │ Population: ... │ │ Population: ... │ │ Population: ... │ │
│ └─────────────────┘ └─────────────────┘ └─────────────────┘ │

│ ┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐ │
│ │ [ FLAG ]        │ │ [ FLAG ]        │ │ [ FLAG ]        │ │
│ │ France          │ │ Brazil          │ │ Norway          │ │
│ │ Region: Europe  │ │ Region: Americas│ │ Region: Europe  │ │
│ ...                                                          │
└──────────────────────────────────────────────────────────────┘

                               « Prev   Page 1 of 10   Next »
```

### 📱 Mobilni layout

```text
┌───────────────────────────────┐
│ 🌍 World Explorer             │
│ [ Dark / Light toggle ]       │
├───────────────────────────────┤

│ [ Search…___________ ]        │
│ [ Region ▼ ]  [ Sort ▼ ]      │

│ Total: 250                    │

│ ┌───────────────────────────┐ │
│ │ [ FLAG ]                  │ │
│ │ Serbia                    │ │
│ │ Europe • Belgrade         │ │
│ │ Population: 6.9M          │ │
│ └───────────────────────────┘ │

│ ┌───────────────────────────┐ │
│ │ [ FLAG ]                  │ │
│ │ Japan                     │ │
│ │ Asia • Tokyo              │ │
│ │ Population: 126M          │ │
│ └───────────────────────────┘ │
...
└───────────────────────────────┘

← Prev        Page 1 of 10        Next →
```

### 🪟 Modal – detalji države (desktop)

```text
┌─────────────────────────────────────────────────────────┐
│ ✕     Serbia                                            │
├─────────────────────────────────────────────────────────┤

│ ┌───────────────┐   Official name: Republic of Serbia   │
│ │   [ FLAG ]    │   Region: Europe                      │
│ │               │   Subregion: Southern Europe          │
│ └───────────────┘   Capital: Belgrade                   │
│                     Population: 6 908 000               │
│                     Languages: Serbian                  │
│                     Currencies: RSD (Dinar)             │
│                     Borders: HUN, ROU, MKD, BIH, ...    │
└─────────────────────────────────────────────────────────┘
```

### 📱 Modal – detalji države (mobilni)

```text
┌───────────────────────────────┐
│ ← Serbia                      │
├───────────────────────────────┤
│ [ LARGE FLAG ]                │

│ Official name: ...            │
│ Region: ...                   │
│ Subregion: ...                │
│ Capital: ...                  │
│ Population: ...               │
│ Languages: ...                │
│ Currencies: ...               │
│ Borders: ...                  │

└───────────────────────────────┘
```

### 🧩 Kartica države (UI sketch)

```text
┌──────────────────────────┐
│ [ FLAG (Full width) ]    │
├──────────────────────────┤
│ Serbia                   │
│ Region: Europe           │
│ Capital: Belgrade        │
│ Population: 6.9M         │
└──────────────────────────┘
```

---

## 🎨 Boje i estetika

(junior može da iskopira paletu)

### Light mode

- Pozadina: `#F5F5F7`
- Kartice: `#FFFFFF`
- Border: `#E5E7EB`
- Tekst: `#111827`
- Sub-tekst: `#6B7280`
- Akcent: `#2563EB`
- Akcent light: `#DBEAFE`

### Dark mode

- Pozadina: `#020617`
- Kartice: `#111827`
- Tekst: `#E5E7EB`
- Sub-tekst: `#9CA3AF`
- Border: `#1F2937`
- Akcent: `#3B82F6`
- Akcent light: `#1D4ED8`

---

## ✏️ Tipografija

- Naslov (header): **1.4rem, bold**
- Naslovi kartica: **0.95rem, bold**
- Body text: **0.85–0.9rem**
- Meta tekst: **0.75–0.8rem, gray**
- Font: `system-ui` (native OS font – brz i moderan)

---

## 🎨 UI Zahtevi (funkcionalno)

### 1. Header

- Naziv aplikacije: **World Explorer**
- Opcioni dark/light toggle (CSS klase)

### 2. Filter bar

- **Search input**: filtrira po imenu države (live search)
- **Region filter**: All / Africa / Americas / Asia / Europe / Oceania / Antarctic
- **Sortiranje**:
  - Name (A–Z)
  - Name (Z–A)
  - Population (asc)
  - Population (desc)

### 3. Info bar

- Prikazuje: `Total countries: X`

### 4. Grid kartica

Kartica treba da sadrži:

- Zastavu (slika full width)
- Naziv države
- Region
- Capital
- Population

Klik na karticu otvara modal sa detaljima.

### 5. Modal — detalji države

Prikazuje:

- Veliku zastavu
- Zvanični naziv
- Region + subregion
- Capital
- Population
- Jezike
- Valute
- Granične zemlje

### 6. Pagination

- 12 država po stranici
- Prev / Next dugmad
- „Page X of Y“

---

## 📐 Responsive Zahtevi

Aplikacija mora da bude prilagođena:

- 📱 Mobilnom (1 kolona)
- 📲 Tabletu (2–3 kolone)
- 🖥 Desktopu (3–4 kolone)

Koristi `@media` query breakpoint-e.

---

## ⚙️ Tehnički Zahtevi

- HTML, CSS, JavaScript (ES6+)
- Možeš koristiti `fetch` ili `axios` za API pozive (po dogovoru)
- CSS organizuj BEM stilom (preporuka):
  - `.header`, `.header__title`, `.card`, `.card__flag`, ...
- JS treba da bude podeljen u logičke funkcije:
  - fetch podataka
  - render svih kartica
  - render jedne kartice
  - filtriranje
  - sortiranje
  - paginacija
  - otvaranje/zatvaranje modala

---

## 🧪 UX / Behavior

- Prilikom prvog učitavanja prikaži loader
- Ako API padne → prikaži poruku:  
  `Unable to load countries. Please try again later.`
- Search + region filter + sort rade u kombinaciji
- Paginacija radi na filtriranim rezultatima

---

## ⭐ Bonus (nije obavezno ali poželjno)

- Dark / Light tema (toggle)
- Animacije na hover i modal transition
- Scroll-to-top dugme
- Čuvanje filtera u `localStorage`

---

## 🏁 Kraj zadatka

Cilj je da napraviš jednostavnu, brzu i preglednu aplikaciju kojom korisnik može da istražuje države sveta, uz moderan UI koji jasno pokazuje tvoje znanje HTML-a, CSS-a i JavaScript-a.

