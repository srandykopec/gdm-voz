# Slovník webových pojmov 📚

Tento dokument obsahuje **kľúčové termíny**, ktoré budeme často používať. Vráť sa k nemu vždy, keď niečomu nerozumieš!

---

## 🔤 Základné skratky (musíš vedieť!)

| Skratka | Celý názov | Vysvetlenie |
|---------|------------|-------------|
| **HTML** | HyperText Markup Language | Jazyk na označenie obsahu (štruktúra stránky) |
| **CSS** | Cascading Style Sheets | Jazyk na štýlovanie (vzhľad stránky) |
| **JS** | JavaScript | Programovací jazyk (interaktivita stránky) |
| **a11y** | Accessibility | Prístupnosť (a + 11 písmen + y) |
| **SEO** | Search Engine Optimization | Optimalizácia pre vyhľadávače (Google) |
| **CDN** | Content Delivery Network | Rýchle servery na načítanie súborov |
| **URL** | Uniform Resource Locator | Adresa webovej stránky (napr. https://...) |

**Jednoducho povedané:**
- **HTML** = čo je na stránke (text, obrázky, odkazy)
- **CSS** = ako to vyzerá (farby, veľkosti, rozloženie)
- **JS** = čo to robí (kliknutia, animácie, načítavanie)

---

## 📄 HTML termíny

| Termín | Vysvetlenie | Príklad |
|--------|-------------|---------|
| **Element** | Stavebný blok HTML (značka + obsah) | `<p>Text</p>` |
| **Tag (značka)** | Otváracie/zatváracie HTML značky | `<div>`, `</div>` |
| **Atribút** | Doplňujúca informácia k elementu | `class="card"`, `href="#"`, `alt="..."` |
| **Hodnota atribútu** | Konkrétna hodnota atribútu | V `class="card"` je `"card"` hodnota |
| **Sémantika** | Značky, ktoré dávajú zmysel (nie len div) | `<header>`, `<nav>`, `<article>`, `<main>` |
| **Landmark** | Orientačné body pre prístupnosť | `<main>`, `<aside>`, `<footer>`, `<nav>` |
| **Inline element** | Prvok, ktorý je vedľa seba (na jednom riadku) | `<span>`, `<a>`, `<strong>`, `<em>` |
| **Block element** | Prvok, ktorý začína na novom riadku | `<div>`, `<p>`, `<h1>`, `<section>` |
| **Self-closing tag** | Značka bez obsahu (sama sa zatvára) | `<img>`, `<br>`, `<hr>`, `<input>` |
| **Nested elements** | Vnorené elementy (element v elemente) | `<div><p>Text</p></div>` |

**Príklad:**
```html
<article class="card">  <!-- Element s atribútom -->
  <h2>Nadpis</h2>       <!-- Vnorený element -->
  <p>Text...</p>
</article>
```

---

## 🎨 CSS termíny

| Termín | Vysvetlenie | Príklad |
|--------|-------------|---------|
| **Selektor (selector)** | Ako vyberieš element na štýlovanie | `.card`, `#header`, `p`, `div > p` |
| **Deklarácia** | Vlastnosť + hodnota | `color: blue;` |
| **Vlastnosť (property)** | Čo chceš zmeniť | `color`, `font-size`, `margin`, `padding` |
| **Hodnota (value)** | Ako to má vyzerať | `blue`, `16px`, `1rem`, `center` |
| **Pravidlo (rule)** | Selektor + blok deklarácií | `.card { color: blue; }` |
| **Kaskáda** | Poradie, v akom sa CSS pravidlá aplikujú | Posledné pravidlo "vyhráva" |
| **Špecifita** | "Sila" selektora (čo má prednosť) | ID (100) > trieda (10) > element (1) |
| **Dedičnosť (inheritance)** | Vlastnosti, ktoré dieťa zdedí od rodiča | `color`, `font-family` (nie margin!) |
| **Box model** | Element = obsah + padding + border + margin | Každý element je "krabica" |
| **Pseudo-class** | Stav elementu (hover, focus...) | `:hover`, `:focus`, `:active`, `:first-child` |
| **Pseudo-element** | Časť elementu (pred/za obsah) | `::before`, `::after`, `::first-letter` |

**Príklad:**
```css
.card {                    /* Selektor */
  color: blue;             /* Vlastnosť: hodnota */
  font-size: 16px;         /* Deklarácia */
}

.card:hover {              /* Pseudo-class */
  color: red;
}
```

**Špecifita (jednoducho):**
- `#header` (ID) je silnejšie než `.header` (trieda)
- `.header` (trieda) je silnejšie než `header` (element)
- Čím špecifickejší selektor, tým "viac vyhráva"

---

## 📦 Box model (musíš pochopiť!)

Každý element má 4 vrstvy:

```
┌─────────────────────────────────┐
│         MARGIN (vonkajší)       │  ← Priestor OKOLO elementu
│  ┌───────────────────────────┐  │
│  │    BORDER (okraj)         │  │  ← Viditeľný okraj
│  │  ┌─────────────────────┐  │  │
│  │  │  PADDING (vnútorný) │  │  │  ← Priestor VNÚTRI elementu
│  │  │  ┌───────────────┐  │  │  │
│  │  │  │   CONTENT     │  │  │  │  ← Obsah (text, obrázok...)
│  │  │  └───────────────┘  │  │  │
│  │  └─────────────────────┘  │  │
│  └───────────────────────────┘  │
└─────────────────────────────────┘
```

**Jednoducho:**
- **Content** = samotný obsah (text, obrázok)
- **Padding** = "vzduchová vankúšik" medzi obsahom a okrajom
- **Border** = viditeľný okraj
- **Margin** = priestor medzi elementami

---

## 🏗️ Layout termíny

| Termín | Vysvetlenie | Príklad |
|--------|-------------|---------|
| **Flexbox** | Rozloženie v jednom smere (riadok ALEBO stĺpec) | `display: flex;` |
| **Grid** | Rozloženie v 2D (riadky A stĺpce) | `display: grid;` |
| **Container** | Obal s maximálnou šírkou (centrovanie obsahu) | `.container { max-width: 1200px; margin: 0 auto; }` |
| **Wrapper** | Ďalší obal (často pre celú sekciu) | `.wrapper` |
| **Responzivita** | Web, ktorý funguje na všetkých veľkostiach | Media queries, mobile-first |
| **Mobile-first** | Začíname od malej obrazovky, potom širšie | `@media (min-width: 768px) { ... }` |
| **Breakpoint** | Bod, kde sa layout mení (napr. 768px) | Mobil (< 768px), Tablet (768–1024px), Desktop (> 1024px) |
| **Viewport** | Viditeľná oblasť prehliadača | `<meta name="viewport" content="width=device-width">` |

**Kedy použiť Flexbox vs. Grid?**
- **Flexbox** → jeden smer (napr. navigácia v riadku, zoznam pod sebou)
- **Grid** → dvoj-rozmerné rozloženie (napr. fotogaléria 3×3)

---

## ♿ Prístupnosť (a11y)

| Termín | Vysvetlenie | Príklad |
|--------|-------------|---------|
| **a11y** | Skratka pre "accessibility" (prístupnosť) | a + 11 písmen + y |
| **Alt text** | Popis obrázka pre screen readery | `<img src="..." alt="Červené tričko">` |
| **Screen reader** | Software, ktorý číta stránku nahlas | Pre zrakovo postihnutých (NVDA, JAWS) |
| **Focus** | Viditeľný okraj pri navigácii klávesnicou | Tab → vidíš, kde si (`:focus`) |
| **Skip link** | Odkaz na preskočenie navigácie | "Preskočiť na obsah" |
| **ARIA** | Atribúty pre lepšiu prístupnosť | `aria-label="Menu"`, `role="navigation"` |
| **Keyboard navigation** | Ovládanie stránky bez myši (Tab, Enter, šípky) | Všetky interaktívne prvky musia byť dostupné |
| **Contrast ratio** | Pomer kontrastu medzi textom a pozadím | Min. 4.5:1 (WCAG AA) |

**Prečo je to důležité?**
- Nie každý používa myš (klávesnica, touch, hlasové ovládanie)
- Nie každý vidí dokonale (farby, veľkosť písma, kontrast)
- Web má byť pre **všetkých** 🌍

---

## 🧩 Komponenty & metodológia

| Termín | Vysvetlenie | Príklad |
|--------|-------------|---------|
| **Komponent** | Opakujúci sa blok na stránke | Karta, tlačidlo, formulár, navigácia |
| **BEM** | Metodológia pomenovania tried | Block__Element--Modifier |
| **Block** | Samostatný komponent (BEM) | `.card` |
| **Element** | Časť komponentu (BEM) | `.card__title`, `.card__image` |
| **Modifier** | Varianta komponentu (BEM) | `.card--featured`, `.btn--primary` |
| **Utility class** | Pomocná trieda (napr. centrovanie) | `.text-center`, `.hidden`, `.mt-2` |
| **State class** | Trieda pre stav (aktívny, skrytý...) | `.is-active`, `.is-hidden`, `.is-loading` |

**BEM príklad:**
```html
<div class="card card--featured">           <!-- Block + Modifier -->
  <img class="card__image" src="..." alt="">  <!-- Element -->
  <h3 class="card__title">Nadpis</h3>        <!-- Element -->
</div>
```

---

## 📐 Jednotky (units)

| Jednotka | Čo to je | Kedy použiť |
|----------|----------|-------------|
| **px** | Pixel (absolútna jednotka) | Borders, presné rozmery (1px, 2px) |
| **%** | Percento (relatívne k rodičovi) | Šírky (width: 50%) |
| **em** | Relatívne k font-size rodiča | Vnútorné medzery (padding, margin) |
| **rem** | Relatívne k root font-size (html) | Font-size, spacing (konzistentné) |
| **vw** | 1% šírky viewportu | Responzívne šírky (width: 80vw) |
| **vh** | 1% výšky viewportu | Full-screen sekcie (height: 100vh) |
| **ch** | Šírka znaku "0" | Max šírka textu (max-width: 65ch) |

**Odporúčanie:**
- **rem** → font-size, spacing (ľahko škálovateľné)
- **%** → šírky kontajnerov
- **px** → borders, shadows (presné hodnoty)
- **vw/vh** → full-screen efekty

---

## 📱 Responzivita & obrázky

| Termín | Vysvetlenie | Príklad |
|--------|-------------|---------|
| **Media query** | Pravidlo pre rôzne veľkosti obrazovky | `@media (min-width: 768px) { ... }` |
| **Breakpoint** | Bod zmeny (mobil → tablet → desktop) | 768px, 1024px |
| **Mobile-first** | Najprv štýly pre mobil, potom desktop | `min-width` (nie `max-width`) |
| **srcset** | Rôzne verzie obrázka pre rôzne obrazovky | `srcset="small.jpg 480w, large.jpg 1200w"` |
| **sizes** | Veľkosť obrázka pri rôznych breakpointoch | `sizes="(max-width: 600px) 100vw, 50vw"` |
| **picture** | Element pre art direction (rôzne výrezy) | `<picture><source>...<img></picture>` |
| **Lazy loading** | Obrázky sa načítajú až keď ich vidíš | `<img loading="lazy">` |

**Media query príklad:**
```css
/* Mobil (predvolené) */
.container {
  width: 100%;
}

/* Tablet a väčšie */
@media (min-width: 768px) {
  .container {
    width: 750px;
  }
}

/* Desktop */
@media (min-width: 1024px) {
  .container {
    width: 1000px;
  }
}
```

---

## 🛠️ Nástroje & pracovný postup

| Termín | Vysvetlenie | Príklad |
|--------|-------------|---------|
| **DevTools (F12)** | Nástroje vývojára v prehliadači | Inšpektor, Console, Network, Lighthouse |
| **Inšpektor (Inspector)** | Pozrieť/upraviť HTML a CSS stránky | Pravý klik → "Preskúmať" |
| **Console** | Výpis chýb a JavaScriptu | Console.log, chybové hlášky |
| **Live Server** | Okamžitý náhľad zmien v prehliadači | VS Code extension (auto-refresh) |
| **Git** | Verzovanie kódu (história zmien) | Commit, push, pull, branch |
| **Repository (repo)** | Priečinok s projektom + Git históriou | Na GitHub-e, GitLab-e... |
| **Commit** | Uložená "snímka" kódu s popisom | `git commit -m "Pridaná navigácia"` |
| **Branch** | Vetva na experimentovanie | `main`, `feature/navbar` |
| **Push** | Nahrať zmeny na server (GitHub) | `git push` |
| **Pull** | Stiahnuť zmeny zo servera | `git pull` |

**Git workflow (jednoducho):**
1. Urobíš zmeny v kóde
2. `git add .` (pridáš do stage)
3. `git commit -m "Popis"` (uložíš snímku)
4. `git push` (nahráš na GitHub)

---

## ⚡ Výkon & optimalizácia

| Termín | Vysvetlenie | Príklad |
|--------|-------------|---------|
| **Minifikácia** | Zmenšenie súboru (odstránenie medzier, komentárov) | `style.min.css` (menší = rýchlejší) |
| **CDN** | Server na rýchle načítanie súborov | Google Fonts, Bootstrap CDN |
| **Cache** | Uloženie súboru v prehliadači (rýchlejšie) | Prehliadač si "pamätá" CSS/obrázky |
| **Compression** | Kompresia súborov (gzip, brotli) | Menší súbor = rýchlejšie načítanie |
| **Critical CSS** | Najdôležitejšie štýly načítané hneď | Above-the-fold content |

---

## 🔍 SEO (základy)

| Termín | Vysvetlenie | Príklad |
|--------|-------------|---------|
| **SEO** | Optimalizácia pre vyhľadávače (Google) | Search Engine Optimization |
| **Meta tag** | Informácie o stránke (description, keywords) | `<meta name="description" content="...">` |
| **Title tag** | Názov stránky (zobrazuje sa v Google) | `<title>Moja stránka - Home</title>` |
| **Heading hierarchy** | Správne poradie H1, H2, H3... | Jedna H1 (hlavný nadpis), potom H2, H3... |
| **Semantic HTML** | Používaj správne značky (nie len div) | `<article>`, `<section>`, `<nav>` |
| **Alt text** | Popis obrázka (Google nevidí obrázky) | `alt="Červené tričko s potlačou"` |
| **Sitemap** | Mapa stránky (zoznam všetkých URL) | `sitemap.xml` |
| **Robots.txt** | Súbor, ktorý hovorí, čo Google má/nemá indexovať | `robots.txt` |

---

## 🎨 Farby & typografia

| Termín | Vysvetlenie | Príklad |
|--------|-------------|---------|
| **Hex** | Hexadecimálny kód farby | `#ff0000` (červená) |
| **RGB** | Red, Green, Blue | `rgb(255, 0, 0)` |
| **RGBA** | RGB + Alpha (priehľadnosť) | `rgba(255, 0, 0, 0.5)` (50% priehľadná) |
| **HSL** | Hue, Saturation, Lightness | `hsl(0, 100%, 50%)` (červená) |
| **Font-family** | Typ písma | `font-family: Arial, sans-serif;` |
| **Font-weight** | Hrúbka písma | `400` (normal), `700` (bold) |
| **Line-height** | Výška riadku (riadkovanie) | `1.5` (150% veľkosti písma) |
| **Letter-spacing** | Medzery medzi písmenami | `0.05em` |

---

## 🚀 Rýchly prehľad (cheat sheet)

**Keď niečomu nerozumieš:**
1. Pozri sa do tohto slovníka 📚
2. Otvor DevTools (F12) a skúšaj 🔧
3. Hľadaj na MDN (developer.mozilla.org) 🌐
4. Opýtaj sa na hodine 💬

**Najdôležitejšie pravidlá:**
- ✅ Sémantické HTML (správne značky)
- ✅ Mobile-first prístup
- ✅ Prístupnosť (alt texty, focus, kontrast)
- ✅ Konzistentné pomenovanie tried (BEM)
- ✅ Box model (padding, margin, border)

---
