# Pomenovanie CSS tried – konvencie a osvedčené postupy 🏷️

Tento dokument ti pomôže orientovať sa v názvoch CSS tried. Obsahuje **zaužívané názvy** (naming conventions), ktoré používa väčšina vývojárov, plus **BEM metodológiu** pre vlastné komponenty.

---

## 🧩 Čo je to komponent? (najprv si to ujasníme!)

**Komponent** = **opakujúci sa, samostatný blok**, ktorý má vlastný účel a môžeš ho použiť viackrát na rôznych miestach stránky.

### 💡 Ako si to predstaviť?

Predstav si stránku ako **stavebnica LEGO**:
- **Celá stránka** = tvoj model (dom, auto...)
- **Komponenty** = jednotlivé kocky, ktoré sa opakujú (okno, dvere, koleso...)

Na webe je to podobne:
- **Stránka** = celý layout (header, main, footer)
- **Komponenty** = karty produktov, tlačidlá, formuláre, navigácia...

---

### 🔍 Ako poznať, že niečo je komponent?

Opýtaj sa:
1. **Opakuje sa to na stránke?** (napr. 10 kariet produktov)
2. **Má to vlastný účel?** (napr. karta = ukázať produkt + obrázok + tlačidlo)
3. **Dá sa to použiť aj inde?** (napr. tá istá karta aj na inej podstránke)

Ak áno → je to komponent! 🎯

---

### 📦 Príklady komponentov:

| Komponent | Čo to je | Kde sa používa |
|-----------|----------|----------------|
| **Karta (card)** | Obrázok + nadpis + text + tlačidlo | Zoznam produktov, blog, team members |
| **Tlačidlo (button)** | Klikateľný prvok na akciu | Všade (formuláre, karty, hero...) |
| **Navigácia (nav)** | Menu s odkazmi | Header, footer, sidebar |
| **Hero sekcia** | Veľký banner s nadpisom + CTA | Domovská stránka, landing page |
| **Formulár (form)** | Vstupné polia + submit tlačidlo | Kontakt, registrácia, prihlásenie |
| **Alert/Notification** | Upozornenie (success/error) | Po odoslaní formulára, chybové hlášky |
| **Modal** | Vyskakovacie okno | Potvrdenie akcie, detail produktu |
| **Avatar** | Profilový obrázok (okrúhly) | Komentáre, užívateľský profil |

---

### 🎨 Príklad: Karta produktu (card)

```html
<!-- Toto je komponent "karta" -->
<div class="card">
  <img class="card__image" src="tricko.jpg" alt="Tričko">
  <h3 class="card__title">Tričko s potlačou</h3>
  <p class="card__price">19,99 €</p>
  <button class="card__button">Do košíka</button>
</div>
```

**Prečo je to komponent?**
- ✅ Opakuje sa (máš 20 produktov → 20× tá istá karta)
- ✅ Má vlastný účel (ukázať produkt)
- ✅ Dá sa použiť aj inde (na inej stránke, v sidebar-e...)

---

### 🏗️ Komponent vs. Layout

| | Layout | Komponent |
|---|--------|-----------|
| **Čo to je** | Štruktúra stránky | Opakujúci sa blok |
| **Príklad** | `.header`, `.main`, `.footer` | `.card`, `.button`, `.nav` |
| **Koľkokrát** | 1× na stránke | Mnohokrát |
| **Účel** | Organizovať priestor | Zobrazovať konkrétny obsah |

**Predstav si to ako dom:**
- **Layout** = múry, strecha, základ (štruktúra domu)
- **Komponenty** = nábytok, lampy, obrázky (veci v dome, ktoré sa opakujú)

---

### 🎯 Praktický tip:

Keď tvoríš web, spýtaj sa:
1. **"Bude sa to opakovať?"** → Ak áno, urob z toho komponent (s BEM triedami).
2. **"Je to len raz na stránke?"** → Použij jednoduchú triedu (napr. `.header`, `.hero`).

**Príklad:**
```html
<!-- Layout (1× na stránke) -->
<header class="header">...</header>

<!-- Komponent (viackrát) -->
<div class="card">...</div>
<div class="card">...</div>
<div class="card">...</div>
```

---

## 📐 BEM metodológia (Block Element Modifier)

**BEM** je systém pomenovania, ktorý ti pomôže udržať kód prehľadný a škálovateľný.

### Syntax:
```css
.block {}              /* Samostatný komponent */
.block__element {}     /* Časť komponentu */
.block--modifier {}    /* Varianta komponentu */
```

### Príklad – karta s produktom:
```html
<div class="card">
  <img class="card__image" src="produkt.jpg" alt="Produkt">
  <h3 class="card__title">Názov produktu</h3>
  <p class="card__text">Krátky popis produktu...</p>
  <button class="card__button card__button--primary">Kúpiť</button>
</div>
```

```css
.card {
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 1rem;
}

.card__image {
  width: 100%;
  height: auto;
}

.card__title {
  font-size: 1.25rem;
  margin-top: 0.5rem;
}

.card__text {
  color: #666;
}

.card__button {
  background: #333;
  color: white;
  padding: 0.5rem 1rem;
  border: none;
  border-radius: 4px;
}

.card__button--primary {
  background: #007bff;
}
```

**Výhody BEM:**
- ✅ Jasná hierarchia (vieš, čo patrí kam)
- ✅ Nízka špecifita (menej konfliktov)
- ✅ Funguje aj na veľkých projektoch
- ✅ Ľahko sa čítá a upravuje

---

## 🏗️ Layout a štruktúra stránky

Tieto názvy sa používajú pre hlavnú štruktúru stránky:

```css
.container       /* Obalový kontajner s max-width (centrovanie obsahu) */
.wrapper         /* Ďalší obal (často pre celú sekciu) */
.section         /* Logická sekcia obsahu */
.header          /* Hlavička stránky (logo, navigácia) */
.footer          /* Pätička (kontakty, copyright) */
.main            /* Hlavný obsah stránky */
.sidebar         /* Bočný panel */
.content         /* Obsahová oblasť */
.grid            /* Grid layout kontajner */
.flex            /* Flexbox layout kontajner */
.row             /* Riadok (napr. v grid systéme) */
.col             /* Stĺpec */
```

### Príklad základnej štruktúry:
```html
<!DOCTYPE html>
<html lang="sk">
<head>
  <meta charset="UTF-8">
  <title>Moja stránka</title>
</head>
<body>
  <header class="header">
    <div class="container">
      <nav class="nav">...</nav>
    </div>
  </header>
  
  <main class="main">
    <div class="container">
      <section class="section">
        <h1>Obsah</h1>
      </section>
    </div>
  </main>
  
  <footer class="footer">
    <div class="container">
      <p>© 2025</p>
    </div>
  </footer>
</body>
</html>
```

---

## 🧭 Navigácia

```css
.nav             /* Navigácia */
.navbar          /* Navigačný bar */
.menu            /* Menu */
.menu__item      /* Položka menu (BEM) */
.breadcrumb      /* Breadcrumb navigácia (Domov > Kategória > Stránka) */
.pagination      /* Stránkovanie (1, 2, 3...) */
```

### Príklad navigácie:
```html
<nav class="nav">
  <ul class="nav__list">
    <li class="nav__item nav__item--active">
      <a href="#" class="nav__link">Domov</a>
    </li>
    <li class="nav__item">
      <a href="#" class="nav__link">O nás</a>
    </li>
    <li class="nav__item">
      <a href="#" class="nav__link">Kontakt</a>
    </li>
  </ul>
</nav>
```

---

## 🧩 Komponenty (opakujúce sa bloky)

```css
.card            /* Karta (obrázok + text + akcia) */
.hero            /* Hero sekcia (veľký banner na začiatku) */
.cta             /* Call-to-action (výzva k akcii) */
.button / .btn   /* Tlačidlo */
.form            /* Formulár */
.input           /* Vstupné pole */
.label           /* Label (popis poľa) */
.alert           /* Upozornenie (success, error, warning) */
.modal           /* Modálne okno (overlay) */
.dropdown        /* Dropdown menu */
.tooltip         /* Tooltip (malá nápoveda) */
.badge           /* Badge/odznak (napr. "Nové", "Zľava") */
.avatar          /* Avatar (profilový obrázok) */
.thumbnail       /* Náhľadový obrázok */
.accordion       /* Akordeón (rozbaľovací obsah) */
.tabs            /* Záložky (prepínanie obsahu) */
.table           /* Tabuľka */
```

### Príklad hero sekcie:
```html
<section class="hero hero--large">
  <div class="container">
    <h1 class="hero__title">Vitaj na našej stránke!</h1>
    <p class="hero__text">Toto je krátky popis toho, čo ponúkame.</p>
    <a href="#" class="btn btn--primary">Začni teraz</a>
  </div>
</section>
```

---

## ✍️ Typografia

```css
.title           /* Hlavný nadpis */
.subtitle        /* Podnadpis */
.text            /* Text */
.caption         /* Popis (napр. pod obrázkom) */
.lead            /* Úvodný text (väčší, zvýraznený) */
.heading         /* Všeobecný nadpis */
```

---

## 🎨 Tlačidlá

```css
.btn             /* Základné tlačidlo */
.btn--primary    /* Primárne (hlavná akcia) */
.btn--secondary  /* Sekundárne */
.btn--danger     /* Nebezpečná akcia (zmazať) */
.btn--success    /* Úspešná akcia */
.btn--large      /* Veľké tlačidlo */
.btn--small      /* Malé tlačidlo */
.btn--disabled   /* Vypnuté tlačidlo */
```

### Príklad:
```html
<button class="btn btn--primary">Odoslať</button>
<button class="btn btn--secondary">Zrušiť</button>
<button class="btn btn--danger">Zmazať</button>
```

---

## 🛠️ Utility triedy (pomocné)

Tieto triedy používaj **šetrne** – sú užitočné na rýchle úpravy, ale nepreháňaj to.

```css
/* Viditeľnosť */
.hidden          /* Skryté (display: none) */
.visible         /* Viditeľné */
.sr-only         /* Len pre screen readery (prístupnosť) */

/* Zarovnanie textu */
.text-center     /* Text na stred */
.text-left       /* Text vľavo */
.text-right      /* Text vpravo */

/* Medzery (spacing) */
.mt-1, .mt-2     /* Margin top (1 = malý, 2 = stredný...) */
.mb-1, .mb-2     /* Margin bottom */
.ml-1, .ml-2     /* Margin left */
.mr-1, .mr-2     /* Margin right */
.p-1, .p-2       /* Padding (všetky strany) */
.pt-1, .pt-2     /* Padding top */
.pb-1, .pb-2     /* Padding bottom */

/* Display */
.flex            /* display: flex */
.block           /* display: block */
.inline          /* display: inline */
.inline-block    /* display: inline-block */

/* Farby */
.text-primary    /* Primárna farba textu */
.text-secondary  /* Sekundárna farba */
.bg-primary      /* Primárne pozadie */
.bg-light        /* Svetlé pozadie */
.bg-dark         /* Tmavé pozadie */
```

---

## 🔄 Stavy (state classes)

Tieto triedy používaj pre **dynamické stavy** (JavaScript, hover, aktívne...).

```css
.is-active       /* Aktívny stav (napr. aktívna stránka v menu) */
.is-disabled     /* Vypnutý stav */
.is-hidden       /* Skrytý (alternatíva k .hidden) */
.is-loading      /* Načítava sa (napr. spinner) */
.is-open         /* Otvorený (napr. dropdown) */
.is-closed       /* Zatvorený */
.has-error       /* Má chybu (napr. formulárové pole) */
.has-success     /* Úspech */
```

### Príklad s JavaScriptom:
```html
<button class="btn btn--primary" id="menuToggle">Menu</button>
<nav class="nav is-hidden" id="menu">...</nav>

<script>
  const toggle = document.getElementById('menuToggle');
  const menu = document.getElementById('menu');
  
  toggle.addEventListener('click', () => {
    menu.classList.toggle('is-hidden');
  });
</script>
```

---

## ✅ Kombinácia BEM + konvencie (najlepší prístup)

**Odporúčam:**
1. **Zaužívané názvy** pre layout: `.header`, `.main`, `.footer`, `.container`, `.nav`
2. **BEM** pre vlastné komponenty: `.card__title`, `.button--primary`
3. **Utility triedy** šetrne: `.text-center`, `.hidden`

### Kompletný príklad:
```html
<body>
  <header class="header">
    <div class="container">
      <nav class="nav">
        <ul class="nav__list">
          <li class="nav__item is-active">
            <a href="#" class="nav__link">Domov</a>
          </li>
          <li class="nav__item">
            <a href="#" class="nav__link">Produkty</a>
          </li>
        </ul>
      </nav>
    </div>
  </header>

  <main class="main">
    <section class="hero hero--large">
      <div class="container">
        <h1 class="hero__title">Vitajte!</h1>
        <p class="hero__text text-center">Toto je náš e-shop.</p>
        <a href="#" class="btn btn--primary">Objavuj</a>
      </div>
    </section>

    <section class="section">
      <div class="container">
        <div class="grid">
          <div class="card">
            <img class="card__image" src="..." alt="Produkt">
            <h3 class="card__title">Produkt 1</h3>
            <p class="card__text">Popis...</p>
            <button class="btn btn--secondary">Detail</button>
          </div>
          <!-- Ďalšie karty -->
        </div>
      </div>
    </section>
  </main>

  <footer class="footer">
    <div class="container text-center">
      <p>© 2025 Moja firma</p>
    </div>
  </footer>
</body>
```

---

## 🎯 Zásady dobrého pomenovania

1. **Používaj anglické názvy** (aj keď píšeš slovenský obsah) – je to štandard komunity
2. **Buď konzistentný** – vyber si systém (BEM) a drž sa ho
3. **Malé písmená a pomlčky** – `.my-class`, nie `.MyClass` ani `.my_class`
4. **Popisné názvy** – `.card__title` (jasné) > `.ct` (nejasné)
5. **Vyhýbaj sa skratkám** (okrem zaužívaných: `.btn`, `.nav`, `.cta`)
6. **Netvor "div-soup"** – radšej sémantické HTML (`<header>`, `<nav>`, `<main>`) + menej tried

---

## 📚 Ďalšie zdroje

- **BEM metodológia:** https://getbem.com/
- **CSS naming conventions:** https://www.freecodecamp.org/news/css-naming-conventions-that-will-save-you-hours-of-debugging-35cea737d849/
- **Tailwind utility classes (inšpirácia):** https://tailwindcss.com/docs

---

**Tip:** Keď začínaš nový projekt, najprv si napíš v komentári "zoznam tried", ktoré budeš používať. Pomôže ti to udržať konzistenciu.

```css
/* Layout */
/* .container, .header, .main, .footer, .section */

/* Komponenty */
/* .card, .btn, .nav, .hero */

/* Utility */
/* .text-center, .hidden, .mt-1 */
```

Držím ti palce! 🚀
