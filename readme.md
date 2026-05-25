# AK Kyzlink – Advokátní kancelář Mgr. Vladimíra Kyzlinka

## 1. Úvod

**Název projektu:** AK Kyzlink  
**Téma:** Webová prezentace advokátní kanceláře Mgr. Vladimíra Kyzlinka se sídlem v Praze 6.  
Web představuje kancelář, její právní služby, tým advokátů, ceník a kontaktní informace.

**Živý web:** https://stepanh10.github.io/ak-kyzlink/

---

## 2. Použité technologie

| Technologie | Verze / poznámka |
|---|---|
| HTML5 | Sémantické značky |
| CSS3 | Vlastní bez frameworku |
| JavaScript | Vanilla JS (ES6+) |
| Google Fonts | Bricolage Grotesque, TikTok Sans |
| AOS | Animate On Scroll (volitelné) |
| IDE | Visual Studio Code |
| Lokální server | Live Server (VS Code rozšíření) |

---

## 3. Adresářová struktura

```
ak-kyzlink/
├── index.html              # Hlavní HTML soubor
├── style.css               # Minifikované styly
├── script.js               # Minifikovaný JavaScript
├── sitemap.xml             # Mapa webu pro vyhledávače
├── robots.txt              # Instrukce pro crawlery
└── ak-kyzlink-images/
    └── images/
        ├── hero.webp
        ├── hero-mobile-gradient.webp
        ├── book.webp
        ├── bg-pattern.webp
        ├── team/
        │   ├── Vladimir.webp
        │   ├── Anna.webp
        │   ├── Stanislava.webp
        │   ├── Lucie.webp
        │   └── Jitka.webp
        └── svg/
            ├── logo.svg
            ├── logo-simple.svg
            ├── chevron.svg
            ├── handbag.svg
            ├── handshake.svg
            ├── house.svg
            ├── server.svg
            ├── work.svg
            ├── papers.svg
            ├── writer.svg
            ├── phone.svg
            └── mail.svg
```

---

## 4. Technický rozbor

### 4.1 Výkon (Performance)

**Teoretický popis:**  
Výkon webu ovlivňuje rychlost načítání a uživatelský zážitek. Klíčové techniky zahrnují optimalizaci obrázků, lazy loading, minifikaci kódu a omezení HTTP požadavků.

**Obrázky ve formátu WebP:**
```html
<img src="/ak-kyzlink-images/images/team/Vladimir.webp" alt="..." loading="lazy" />
```
Formát `.webp` nabízí až o 30 % menší velikost oproti `.jpg` při stejné kvalitě.

**Lazy loading:**
```html
<img src="fotka.webp" loading="lazy" alt="popis" />
```
Obrázky se načítají až při scrollování k nim, čímž se zkracuje čas prvního načtení stránky.

**Minifikace CSS a JS:**  
CSS a JavaScript soubory jsou minifikovány – odstraněny mezery, komentáře a zalomení řádků. Výsledkem je menší velikost souborů a rychlejší přenos.

---

### 4.2 SEO

**Teoretický popis:**  
SEO (Search Engine Optimization) zajišťuje, že web je správně indexován vyhledávači. Zahrnuje sémantické HTML, meta tagy, strukturovaná data, sitemap a robots.txt.

**Meta tagy:**
```html
<meta name="description" content="Advokátní kancelář Mgr. Vladimíra Kyzlinka – Praha 6" />
<meta name="keywords" content="advokát, Praha, korporátní právo, nemovitosti" />
<link rel="canonical" href="https://ak-kyzlink.cz" />
```

**Strukturovaná data (Schema.org):**
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "LegalService",
  "name": "Advokátní kancelář Mgr. Vladimíra Kyzlinka",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "Mařákova 263/3",
    "addressLocality": "Praha 6"
  },
  "telephone": "+420222518156"
}
</script>
```
Strukturovaná data pomáhají vyhledávačům pochopit obsah stránky a zobrazit rozšířené výsledky.

**sitemap.xml** informuje vyhledávače o struktuře webu.  
**robots.txt** říká crawlerům co mohou a nemohou indexovat.

---

### 4.3 Přístupnost (Accessibility)

**Teoretický popis:**  
Přístupný web je použitelný pro všechny uživatele včetně osob se zdravotním postižením. Standardy WCAG 2.1 definují požadavky na kontrast, ovladatelnost klávesnicí a podporu čteček obrazovky.

**ARIA atributy:**
```html
<button class="burger" aria-label="Otevřít menu" aria-expanded="false" aria-controls="mobile-menu">
```
`aria-label` popisuje tlačítko pro čtečky obrazovky. `aria-expanded` informuje o stavu menu.

**Alt texty na obrázcích:**
```html
<img src="Vladimir.webp" alt="fotka Mgr. Vladimír Kyzlink" />
```

**Skip link:**
```html
<a href="#sluzby" class="skip-link">Přeskočit na obsah</a>
```
Umožňuje uživatelům klávesnice přeskočit navigaci přímo na hlavní obsah.

**Zavírání modalu klávesou Escape:**
```javascript
document.addEventListener("keydown", (e) => {
    if (e.key === "Escape") {
        closeModal(teams);
        closeModal(sluzby);
    }
});
```

---

### 4.4 Sociální sítě (Open Graph & Twitter Cards)

**Teoretický popis:**  
Open Graph protokol umožňuje kontrolovat jak se web zobrazuje při sdílení na sociálních sítích (Facebook, LinkedIn). Twitter Cards plní stejnou funkci pro X (Twitter).

**Open Graph:**
```html
<meta property="og:title" content="Advokátní kancelář Mgr. Vladimíra Kyzlinka" />
<meta property="og:description" content="Právní služby v Praze" />
<meta property="og:image" content="https://ak-kyzlink.cz/ak-kyzlink-images/images/hero.webp" />
<meta property="og:url" content="https://ak-kyzlink.cz" />
<meta property="og:type" content="website" />
```

**Twitter Cards:**
```html
<meta name="twitter:card" content="summary_large_image" />
<meta name="twitter:title" content="Advokátní kancelář Mgr. Vladimíra Kyzlinka" />
<meta name="twitter:image" content="https://ak-kyzlink.cz/ak-kyzlink-images/images/hero.webp" />
```

---

### 4.5 UI/UX

**Teoretický popis:**  
Responzivní design zajišťuje správné zobrazení na všech zařízeních. Mobile First přístup znamená že základní styly jsou pro mobil a větší obrazovky se přizpůsobují přes media queries.

**Responzivní grid služeb:**
```css
.sluzby_grid {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
}

@media (max-width: 768px) {
    .sluzby_container {
        width: calc(50% - 20px);
    }
}

@media (max-width: 480px) {
    .sluzby_container {
        width: 100%;
    }
}
```

**Interaktivní hover efekty:**
```css
.sluzby_container:hover {
    background-color: #d09984;
    transition: background-color 0.3s ease;
}
```

**Modální okna pro detail týmu a služeb** – kliknutím na kartu se otevře popup s detailními informacemi bez přechodu na novou stránku.

---

### 4.6 AI Integrace

**Teoretický popis:**  
Umělá inteligence byla využita jako pomocný nástroj při vývoji, analýze kódu a tvorbě obsahu. AI neznahradila rozhodování vývojáře, ale urychlila a zkvalitnila práci.

*[Doplňte konkrétní příklady z AI Deníku níže]*

---

## 5. AI Deník

Přehled promptů a jejich přínos pro projekt:

| Prompt | Co AI přinesla |
|---|---|
| *"Optimalizuj web pro telefony bez použití JS a CSS frameworku"* | Návrh responzivního HTML a CSS s media queries |
| *[Doplňte další prompty]* | *[Doplňte popis]* |

---

## 6. Instalace a spuštění

### Požadavky
- Visual Studio Code
- Rozšíření **Live Server** (ms-vscode.live-server)

### Kroky

1. Stáhni nebo naklonuj repozitář:
```bash
git clone https://github.com/TVUJ-UCET/ak-kyzlink.git
```

2. Otevři složku ve VS Code:
```bash
code ak-kyzlink
```

3. Klikni pravým tlačítkem na `index.html` → **Open with Live Server**

4. Web se otevře na adrese:
```
http://127.0.0.1:5500
```

---

## 7. Galerie

### Desktop verze

![alt text](image.png)

![alt text](image-1.png)

![alt text](image-2.png)

![alt text](image-3.png)
### Mobilní verze

*[Vlož screenshot mobilní verze]*

### Klíčové funkce

**Modal – detail člena týmu**  
*[Vlož screenshot otevřeného modalu]*

**Modal – detail služby**  
*[Vlož screenshot otevřeného modalu služby]*

**Hamburger menu – mobilní navigace**  
*[Vlož screenshot otevřeného menu na mobilu]*
