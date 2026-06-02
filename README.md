<div align="center">
<img src="./header.svg" width="100%" alt="CSS Theory Assignment"/>
</div>


<br/>


---

## 📌 Table of Contents

| # | Question | Level | Marks |
|:-:|----------|:-----:|:-----:|
| [01](#-q1--what-is-css--how-to-add-it) | What is CSS & How to Add It | 🟢 Beginner | 5 |
| [02](#-q2--css-selectors) | CSS Selectors | 🟢 Beginner | 8 |
| [03](#-q3--css-box-model) | CSS Box Model | 🟢 Beginner | 7 |
| [04](#-q4--css-colors) | CSS Colors | 🟢 Beginner | 6 |
| [05](#-q5--css-units) | CSS Units | 🟢 Beginner | 7 |
| [06](#-q6--specificity--cascade) | Specificity & Cascade | 🟡 Intermediate | 8 |
| [07](#-q7--css-flexbox) | CSS Flexbox | 🟡 Intermediate | 10 |
| [08](#-q8--pseudo-classes--pseudo-elements) | Pseudo-classes & Pseudo-elements | 🟡 Intermediate | 9 |
| [09](#-q9--transitions--animations) | Transitions & Animations | 🔴 Advanced | 10 |
| [10](#-q10--responsive-web-design) | Responsive Web Design | 🔴 Advanced | 10 |

---

<div align="center">

### 〔 🟢 BEGINNER · Q1 — Q5 〕

</div>

---

## 🎯 Q1 · What is CSS & How to Add It

> **CSS (Cascading Style Sheets)** is the styling language of the web. It separates visual presentation from HTML structure — giving developers precise control over layout, color, typography, spacing, and animation. Without CSS, every webpage is an unstyled wall of text.

### 🧩 Keyword Concepts

| Keyword | Meaning |
|---------|---------|
| `Cascading` | Styles flow from parent → child; later rules can override earlier ones |
| `Separation of Concerns` | HTML = structure, CSS = presentation, JS = behaviour |
| `Render Engine` | The browser parses CSS and paints pixels based on computed styles |
| `Specificity` | The scoring system that decides which rule wins when two conflict |

---

### 📐 Three Methods of Adding CSS

#### ① External CSS — `<link>` tag ✅ Industry Standard

```html
<!-- index.html -->
<head>
  <link rel="stylesheet" href="styles.css" />
</head>
```

```css
/* styles.css */
body {
  font-family: 'Segoe UI', sans-serif;
  background-color: #0f172a;
  color: #f1f5f9;
  margin: 0;
}
```

#### ② Internal CSS — `<style>` block ⚠️ Single-page only

```html
<head>
  <style>
    h1 {
      color: #7c3aed;
      font-size: 2rem;
    }
  </style>
</head>
```

#### ③ Inline CSS — `style=""` attribute ❌ Avoid

```html
<p style="color: #db2777; font-size: 14px;">Avoid this in real projects.</p>
```

---

### 🏆 Method Comparison

| Criterion | External ✅ | Internal ⚠️ | Inline ❌ |
|-----------|:-----------:|:-----------:|:--------:|
| Reusable across pages | ✅ | ❌ | ❌ |
| Browser caches the file | ✅ | ❌ | ❌ |
| Clean HTML structure | ✅ | ⚠️ | ❌ |
| Team-friendly | ✅ | ⚠️ | ❌ |
| Overrides everything | — | — | ✅ (bad) |

> 💡 **Why External CSS wins:** One `.css` file serves thousands of pages. The browser downloads it once, caches it, and reuses it — zero repeat downloads. Inline styles carry the highest specificity (1000 pts) making them nearly impossible to override without `!important`, which breaks the cascade entirely.

### 🖼️ Visual Reference
> ![CSS Methods](https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=800&q=80)
> *Unsplash — CSS transforms raw HTML into polished, designed interfaces*

---

## 🎯 Q2 · CSS Selectors

> CSS Selectors are **targeting patterns** — they tell the browser exactly which HTML element(s) to style. Every CSS rule begins with a selector. Mastering selectors means mastering CSS.

### 🧩 Key Answers

| Question | Answer |
|----------|--------|
| Class vs ID — which has higher specificity? | **ID** — `#id` scores 100 pts vs `.class` at 10 pts |
| Direct child vs any descendant? | `>` targets direct child only · space targets any descendant |
| Same class on multiple elements? | ✅ Yes — classes are designed to be reusable |
| Same ID on multiple elements? | ❌ No — one ID per page, enforced by HTML spec |

---

### 📐 All 7 Selector Types

```css
/* 1. ELEMENT — targets every matching tag on the page */
p {
  font-size: 1rem;
  line-height: 1.7;
  color: #334155;
}

/* 2. CLASS — targets any element with class="card" (reusable) */
.card {
  background: #1e293b;
  border-radius: 12px;
  padding: 1.5rem;
  border: 1px solid #334155;
}

/* 3. ID — targets the one unique element with id="hero" */
#hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

/* 4. GROUP — one rule, multiple targets (DRY principle) */
h1, h2, h3, h4 {
  font-family: 'Georgia', serif;
  color: #7c3aed;
  margin-bottom: 0.75rem;
}

/* 5. DESCENDANT — <p> anywhere inside .card, however deep */
.card p {
  color: #94a3b8;
  font-size: 0.95rem;
}

/* 6. CHILD (>) — ONLY direct <li> children of <ul>, not grandchildren */
ul > li {
  padding: 0.5rem 0;
  border-bottom: 1px solid #e2e8f0;
}

/* 7. UNIVERSAL (*) — every single element on the page */
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
```

---

### 🆚 Class vs ID — Decision Rule

```css
/* USE CLASS → component styling, reused across multiple elements */
.btn-primary {
  background: #7c3aed;
  color: #fff;
  padding: 0.75rem 1.5rem;
  border-radius: 8px;
  cursor: pointer;
}

/* USE ID → unique landmark / JavaScript hook / page anchor */
#main-nav {
  position: sticky;
  top: 0;
  z-index: 999;
  background: #0f172a;
}
```

> 💡 **Rule:** Default to classes always. Use IDs only for JavaScript `getElementById()` calls or `href="#section"` anchor links where uniqueness is structurally required.

### 🖼️ Visual Reference
> ![CSS Selectors](https://images.unsplash.com/photo-1555066931-4365d14bab8c?w=800&q=80)
> *Unsplash — Code structure showing CSS targeting hierarchy*

---

## 🎯 Q3 · CSS Box Model

> Every HTML element rendered on screen is a **rectangular box**. The CSS Box Model defines how that box is sized and spaced. Misunderstanding it causes 80% of all layout bugs.

### 🧩 Key Answers

| Question | Answer |
|----------|--------|
| Innermost layer? | **Content** — where text and images actually live |
| Padding — inside or outside border? | **Inside** the border, part of the element's background |
| `margin: 0 auto` on a block element? | Sets top/bottom margin to 0 and centers it horizontally |
| With `border-box` does width include padding? | ✅ Yes — width = content + padding + border combined |

---

### 📐 The Four Layers — Visualised

```
╔═══════════════════════════════════════════════╗  ← MARGIN
║  (always transparent — creates space outside) ║
║  ╔═════════════════════════════════════════╗  ║  ← BORDER
║  ║  (visible frame: color, width, style)  ║  ║
║  ║  ╔═══════════════════════════════════╗  ║  ║  ← PADDING
║  ║  ║  (breathing room, bg color shows) ║  ║  ║
║  ║  ║  ╔═════════════════════════════╗  ║  ║  ║  ← CONTENT
║  ║  ║  ║   text · images · children  ║  ║  ║  ║
║  ║  ║  ╚═════════════════════════════╝  ║  ║  ║
║  ║  ╚═══════════════════════════════════╝  ║  ║
║  ╚═════════════════════════════════════════╝  ║
╚═══════════════════════════════════════════════╝
```

| Layer | Controls | Transparent? |
|-------|----------|:------------:|
| **Content** | Text, images, children | — |
| **Padding** | Inner breathing room | ❌ (bg color shows) |
| **Border** | Visible frame around element | ❌ |
| **Margin** | Space between elements | ✅ Always |

---

### 📐 `content-box` vs `border-box`

```css
/* ❌ content-box — DEFAULT, confusing */
/* width: 300px = content only */
/* Actual rendered size: 300 + 40 (padding) + 4 (border) = 344px */
.misleading-box {
  box-sizing: content-box;
  width: 300px;
  padding: 20px;
  border: 2px solid #7c3aed;
}

/* ✅ border-box — PROFESSIONAL STANDARD */
/* width: 300px = total rendered size, always predictable */
/* Content auto-shrinks: 300 - 40 - 4 = 256px of content space */
.box {
  box-sizing: border-box;
  width: 300px;
  padding: 20px;
  border: 2px solid #7c3aed;
  margin: 16px;
  background: #1e293b;
  color: #f1f5f9;
  border-radius: 8px;
}
```

> 💡 **Global reset used in every modern project:**
> ```css
> *, *::before, *::after { box-sizing: border-box; }
> ```
> This one line eliminates layout math confusion across the entire codebase.

### 🖼️ Visual Reference
> ![Box Model](https://images.unsplash.com/photo-1537432376769-00f5c2f4c8d2?w=800&q=80)
> *Unsplash — Browser DevTools showing the Box Model inspector*

---

## 🎯 Q4 · CSS Colors

> Color is the **emotional layer** of UI design. CSS offers five distinct color syntaxes — each serving a different use case. Knowing which to use, and when, is a mark of CSS fluency.

### 🧩 Key Answers

| Question | Answer |
|----------|--------|
| Most commonly used format? | **HEX** — short, copyable, universally supported |
| 'A' in RGBA stands for? | **Alpha** — controls transparency (0 = invisible, 1 = fully opaque) |
| Does `opacity` affect child elements? | ✅ Yes — children inherit the parent's opacity value |
| Does `rgba` alpha affect children? | ❌ No — only that element's background is transparent |

---

### 📐 Five Color Formats — All Showing `#F97316` (Orange)

```css
/* 1. NAMED — human-readable, limited to ~140 predefined colors */
.named  { color: orangered; }                    /* closest named match */

/* 2. HEX — 6 hex digits (RR GG BB), most widely used */
.hex    { color: #F97316; }                      /* ✅ copy-paste from Figma */

/* 3. RGB — red, green, blue each from 0–255 */
.rgb    { color: rgb(249, 115, 22); }

/* 4. RGBA — RGB + alpha transparency channel */
.rgba   { color: rgba(249, 115, 22, 0.85); }    /* 85% opaque */

/* 5. HSL — hue (0–360°), saturation %, lightness % */
.hsl    { color: hsl(24, 94%, 53%); }            /* most intuitive for design */
```

---

### 📐 `opacity` vs `rgba` — Critical Distinction

```css
/* ❌ opacity: 0.5 — the ENTIRE element fades, including text and children */
.overlay-bad {
  background: #000;
  opacity: 0.5;        /* child text also becomes 50% visible — unintended */
}

/* ✅ rgba alpha — ONLY this background is semi-transparent */
/* Children (text, images) remain fully opaque */
.overlay-good {
  background: rgba(0, 0, 0, 0.5);   /* dark see-through background */
  color: #ffffff;                    /* text remains 100% solid */
}
```

> 💡 **Rule:** Use `rgba()` or `color` with alpha for overlays, glassmorphism, and cards. Reserve `opacity` only when you deliberately want the entire element — content, children, everything — to fade together (e.g. a disabled button at 40% opacity).

### 🖼️ Visual Reference
> ![CSS Colors](https://images.unsplash.com/photo-1513542789411-b6a5d4f31634?w=800&q=80)
> *Unsplash — Color palette and design token system in modern UI*

---

## 🎯 Q5 · CSS Units

> CSS units are the **measurement vocabulary** of layout. Choosing the wrong unit breaks responsiveness. Choosing correctly makes your UI scale fluidly across every screen size, zoom level, and user preference.

### 🧩 Key Answers

| Question | Answer |
|----------|--------|
| What is `1rem` by default? | **16px** — equal to the browser root font size |
| `%` is relative to? | The **parent element's** corresponding dimension |
| `vh` stands for? | **Viewport Height** — 1vh = 1% of the browser window height |
| Why `rem` over `px` for font-size? | `rem` respects user browser zoom/accessibility settings; `px` ignores them |

---

### 📐 Six Units — Reference Table

| Unit | Relative To | Best Used For | Example |
|------|-------------|---------------|---------|
| `px` | Nothing (absolute) | Borders, box-shadows, icon sizes | `border: 1px solid` |
| `%` | Parent's size | Fluid widths, image fills | `width: 100%` |
| `rem` | Root `<html>` font-size | Font sizes, spacing scales | `font-size: 1.5rem` |
| `em` | Current element's font-size | Padding/margin relative to text | `padding: 0.75em 1em` |
| `vh` | Viewport height | Hero sections, full-screen areas | `min-height: 100vh` |
| `vw` | Viewport width | Full-bleed layouts, fluid type | `font-size: 5vw` |

---

### 📐 The Golden Rules + Hero Code Task

```css
/*
  📐 GOLDEN RULES
  ─────────────────────────────────────────
  Font sizes    →  rem   (accessibility safe)
  Widths        →  %     (fluid, parent-relative)
  Full sections →  vh    (fills exactly the screen)
  Borders       →  px    (pixel-sharp precision)
  Component gap →  rem   (scales with root font)
*/

/* Hero section using the right unit for every property */
.hero {
  min-height: 100vh;                          /* fills viewport — vh */
  width: 100%;                                /* fills parent — % */
  max-width: 80rem;                           /* ~1280px, zoom-aware — rem */
  margin: 0 auto;                             /* centers horizontally */
  padding: 2rem 1.5rem;                       /* scales with root — rem */
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.hero h1 {
  /* clamp(min, preferred, max) — fluid without media queries */
  font-size: clamp(2rem, 5vw, 4.5rem);       /* fluid — vw scales with screen */
  line-height: 1.15;
  margin-bottom: 1.5rem;                      /* spacing — rem */
}

.hero p {
  font-size: clamp(1rem, 2.5vw, 1.25rem);    /* body fluid scaling */
  max-width: 48rem;                           /* readable line length — rem */
}
```

> 💡 **`clamp(min, preferred, max)`** is the modern industry standard for fluid typography. It replaces breakpoint-based font sizing and makes text scale smoothly between any two screen sizes.

### 🖼️ Visual Reference
> ![CSS Units](https://images.unsplash.com/photo-1498050108023-c5249f4df085?w=800&q=80)
> *Unsplash — Multi-device responsive layout demonstrating CSS unit scaling*

---

<div align="center">

### 〔 🟡 INTERMEDIATE · Q6 — Q8 〕

</div>

---

## 🎯 Q6 · Specificity & Cascade

> When two CSS rules compete for the same element, the browser uses **specificity scoring** to decide the winner. Understanding this system eliminates the temptation to reach for `!important` and reveals how the cascade truly works.

### 🧩 Key Answers

| Question | Answer |
|----------|--------|
| Class vs element — which wins? | **Class** — 10 pts vs element's 1 pt |
| Inline style specificity score? | **1000** — overrides all external/internal rules |
| Equal specificity — which rule wins? | **Source order** — the rule declared last wins |
| What does `!important` override? | Everything — inline styles, IDs, classes, elements |

---

### 📐 Specificity Scoring System

```
┌──────────────────────────────────────────────────────────┐
│  COLUMN  [A]    [B]     [C]     [D]                      │
│                                                          │
│  [A]  Inline styles          →  1000 pts                 │
│  [B]  ID selectors           →   100 pts each            │
│  [C]  Class, attribute,                                  │
│       pseudo-class           →    10 pts each            │
│  [D]  Element, pseudo-element →    1 pt each             │
│                                                          │
│  Universal (*)               →     0 pts                 │
│  !important                  →  ∞  (nuclear override)    │
└──────────────────────────────────────────────────────────┘
```

| Selector | Score | Why |
|----------|:-----:|-----|
| `*` | 0 | Universal, no points |
| `p` | 1 | One element |
| `.card` | 10 | One class |
| `p.card` | 11 | Element + class |
| `#hero` | 100 | One ID |
| `style="..."` | 1000 | Inline |
| `!important` | ♾️ | Overrides all |

---

### 📐 How the Cascade Works — Three Pillars

```
PILLAR 1 → SPECIFICITY   (score-based winner)
PILLAR 2 → SOURCE ORDER  (last declaration wins, if equal score)
PILLAR 3 → INHERITANCE   (color, font-size pass to children automatically)
```

---

### 📐 Code Task — Which Color Wins?

```html
<p id="intro" class="text">Hello</p>
```

```css
/* RULE 1 — element selector — Score: 001 */
p {
  color: #94a3b8;        /* LOSES — lowest score */
}

/* RULE 2 — class selector — Score: 010 */
.text {
  color: #06b6d4;        /* MIDDLE — beats element, loses to ID */
}

/* RULE 3 — ID selector — Score: 100 */
#intro {
  color: #7c3aed;        /* ✅ WINS — highest specificity score */
}
```

> 🏆 **Winner: `color: #7c3aed`** — The ID `#intro` scores 100 pts, dominating `.text` (10) and `p` (1). The cascade evaluates specificity first, source order only as a tiebreaker.

---

### ⚠️ Why `!important` is an Anti-Pattern

```css
/* ❌ ANTI-PATTERN — now impossible to override cleanly */
.button { background: red !important; }

/* ✅ PROFESSIONAL FIX — increase specificity structurally */
.navbar .button { background: red; }   /* score: 11, clean and overrideable */
```

> 💡 **If you need `!important`, your CSS architecture is broken.** Fix the selector structure instead. The only legitimate use of `!important` is in utility classes (like `.hidden { display: none !important }`) where override prevention is intentional.

### 🖼️ Visual Reference
> ![Specificity](https://images.unsplash.com/photo-1461749280684-dccba630e2f6?w=800&q=80)
> *Unsplash — Browser DevTools computed styles showing cascade resolution*

---

## 🎯 Q7 · CSS Flexbox

> Flexbox is the **primary 1-dimensional layout engine** in modern CSS. It replaced float-based hacks and table layouts. Every professional codebase uses Flexbox for UI alignment — navbars, card rows, centering, and more.

### 🧩 Key Answers

| Question | Answer |
|----------|--------|
| `justify-content` vs `align-items`? | `justify-content` = **main axis** · `align-items` = **cross axis** |
| What does `flex: 1` do? | Item grows and shrinks equally to fill all available space |
| Center both axes with Flexbox? | `justify-content: center` + `align-items: center` on the container |
| `flex-wrap: wrap` does what? | Items wrap onto the next row when they exceed the container width |

---

### 📐 Block Layout vs Flexbox

```css
/* ❌ OLD — float-based, causes parent collapse, manual clearfix needed */
.old-nav div {
  float: left;
  margin-right: 1rem;
}

/* ✅ MODERN — Flexbox, declarative, self-contained, no hacks */
.flex-nav {
  display: flex;            /* activates Flexbox context */
  align-items: center;      /* vertical center on cross axis */
  gap: 1.5rem;              /* space between items, no margin hacks */
}
```

---

### 📐 Core Flexbox Properties

```css
.container {
  display: flex;                   /* ← activates Flexbox */

  /* DIRECTION */
  flex-direction: row;             /* row | column | row-reverse | column-reverse */

  /* MAIN AXIS (horizontal when row) */
  justify-content: space-between;  /* flex-start | center | flex-end | space-between | space-around | space-evenly */

  /* CROSS AXIS (vertical when row) */
  align-items: center;             /* flex-start | center | flex-end | stretch | baseline */

  /* WRAPPING */
  flex-wrap: wrap;                 /* nowrap (default) | wrap | wrap-reverse */

  /* SPACING */
  gap: 1.5rem;                     /* shorthand for row-gap + column-gap */
}

.item {
  /* flex: grow  shrink  basis */
  flex: 1;          /* equivalent to flex: 1 1 0% — grows/shrinks equally */
  flex: 0 0 200px;  /* fixed 200px — does not grow or shrink */
}
```

---

### 📐 Code Task — Professional Navbar

```html
<nav class="navbar">
  <div class="logo">MyBrand</div>
  <ul class="nav-links">
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Projects</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>
```

```css
.navbar {
  display: flex;
  justify-content: space-between;  /* logo left, links right */
  align-items: center;             /* vertically centred */
  padding: 1rem 2rem;
  background: #0f172a;
  border-bottom: 1px solid #1e293b;
  position: sticky;
  top: 0;
  z-index: 100;
}

.logo {
  font-size: 1.4rem;
  font-weight: 700;
  color: #7c3aed;
  letter-spacing: -0.5px;
}

.nav-links {
  display: flex;           /* horizontal row of links */
  gap: 2rem;               /* space between each link */
  list-style: none;
  margin: 0;
  padding: 0;
}

.nav-links a {
  color: #94a3b8;
  text-decoration: none;
  font-size: 0.95rem;
  transition: color 0.2s ease;
}

.nav-links a:hover { color: #f1f5f9; }
```

---

### 📐 Two Real-World Use Cases

```css
/* USE CASE 1 — Perfect modal centering */
.modal-overlay {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background: rgba(0,0,0,0.6);
}

/* USE CASE 2 — Responsive card grid that wraps */
.card-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 1.5rem;
}
.card-grid .card {
  flex: 1 1 280px;     /* grow, shrink, never narrower than 280px */
}
```

### 🖼️ Visual Reference
> ![Flexbox](https://images.unsplash.com/photo-1547658719-da2b51169166?w=800&q=80)
> *Unsplash — Modern navbar and responsive card layout built with Flexbox*

---

## 🎯 Q8 · Pseudo-classes & Pseudo-elements

> Pseudo-classes respond to **state and position**. Pseudo-elements create **virtual content**. Together they power interactive UI, decorative effects, and state-based styling — without a single line of JavaScript.

### 🧩 Key Answers

| Question | Answer |
|----------|--------|
| Does `::before` add a real HTML element? | ❌ No — it is virtual, invisible in the DOM inspector |
| Required property for `::before/::after`? | **`content`** — even `content: ""` (empty string) is mandatory |
| `:nth-child(2n)` selects which? | All **even-numbered** children — 2nd, 4th, 6th… |
| Style every 3rd list item? | `li:nth-child(3n)` |

---

### 📐 Syntax Rule

```
:   single colon   →  Pseudo-CLASS   — state or position based
                      :hover  :focus  :nth-child()  :not()

::  double colon   →  Pseudo-ELEMENT — virtual content injection
                      ::before  ::after  ::placeholder  ::selection
```

---

### 📐 Pseudo-classes with Examples

```css
/* :hover — mouse moves over element */
.btn:hover {
  background: #db2777;
  transform: translateY(-2px);
  transition: all 0.2s ease;
}

/* :focus — element receives keyboard or click focus */
input:focus {
  outline: 2px solid #7c3aed;
  outline-offset: 2px;
  border-color: transparent;
}

/* :nth-child() — position-based targeting */
li:nth-child(3n)   { color: #7c3aed; }   /* every 3rd item */
li:nth-child(odd)  { background: #f8fafc; }
li:nth-child(2n)   { background: #f1f5f9; } /* even rows */

/* :not() — select everything EXCEPT the match */
.nav-link:not(.active) {
  opacity: 0.65;
}
```

---

### 📐 Pseudo-elements with Examples

```css
/* ::before — injects virtual node BEFORE content */
.featured::before {
  content: "★ ";          /* content is REQUIRED — even if empty */
  color: #f97316;
  font-size: 1.1em;
}

/* ::after — injects virtual node AFTER content */
.section-title::after {
  content: "";
  display: block;
  width: 48px;
  height: 3px;
  background: #7c3aed;
  margin-top: 8px;
  border-radius: 2px;
}

/* ::placeholder — styles input placeholder text */
input::placeholder {
  color: #94a3b8;
  font-style: italic;
  font-size: 0.9rem;
}
```

---

### 📐 Code Task — Button, Star & Placeholder

```css
/* ① Button turns orange on hover */
.btn {
  background: #1e293b;
  color: #f1f5f9;
  padding: 0.75rem 1.5rem;
  border: 1px solid #334155;
  border-radius: 8px;
  cursor: pointer;
  font-size: 0.95rem;
  transition: background 0.25s ease, transform 0.2s ease;
}
.btn:hover {
  background: #f97316;          /* ✅ orange on hover */
  transform: translateY(-1px);
}

/* ② Star before every .featured list item */
li.featured::before {
  content: "★ ";               /* ✅ virtual star — no HTML needed */
  color: #f97316;
  font-weight: bold;
}

/* ③ Placeholder styled grey */
input[type="text"]::placeholder,
input[type="email"]::placeholder {
  color: #94a3b8;               /* ✅ muted grey placeholder */
  font-style: italic;
}
```

### 🖼️ Visual Reference
> ![Pseudo-classes](https://images.unsplash.com/photo-1593720219276-0b1eacd0aef4?w=800&q=80)
> *Unsplash — Hover states, focus rings, and interactive UI feedback*

---

<div align="center">

### 〔 🔴 ADVANCED · Q9 — Q10 〕

</div>

---

## 🎯 Q9 · Transitions & Animations

> CSS motion is the difference between an interface that feels **alive** and one that feels static. Transitions handle state changes. Animations handle sequences. Both should always prefer `transform` and `opacity` for GPU-accelerated, jank-free motion.

### 🧩 Key Answers

| Question | Answer |
|----------|--------|
| Common transition triggers? | `:hover`, `:focus`, `:active`, JS class toggle |
| Multiple transitions on one element? | ✅ Yes — comma-separated list |
| `animation-iteration-count: infinite`? | Loops forever — ideal for loaders and pulses |
| Why `transform` faster than `width`? | `transform` runs on the GPU compositor — no layout recalculation |

---

### 📐 Transitions vs Animations

| Feature | Transition | Animation |
|---------|:----------:|:---------:|
| Needs a trigger? | ✅ Yes | ❌ No — runs automatically |
| Direction | A → B only | Multi-step via `@keyframes` |
| Can loop? | ❌ | ✅ `iteration-count` |
| Fill mode? | N/A | ✅ `animation-fill-mode` |
| Best for | Hover effects, focus | Page load reveals, loaders |

---

### 📐 Transition Syntax & Timing Functions

```css
/* shorthand: property   duration   timing-function   delay */
.card {
  transition: transform 0.3s ease-out 0s,
              box-shadow 0.3s ease-out 0s;
}

/*
  TIMING FUNCTIONS — how speed changes over time:
  ─────────────────────────────────────────────────
  ease        → slow start, fast middle, slow end  (natural, default)
  ease-in     → slow start, accelerates            (element entering)
  ease-out    → fast start, decelerates            ✅ most natural for hovers
  linear      → constant speed                     (spinners, progress bars)
  cubic-bezier(x1,y1,x2,y2) → fully custom curve  (spring, bounce, elastic)
*/
```

---

### 📐 `@keyframes` & Animation Properties

```css
/* Define animation sequence with @keyframes */
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(28px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/*
  animation shorthand:
  name  duration  timing  delay  iteration  fill-mode
*/
.element {
  animation: fadeInUp 0.55s ease-out 0.1s 1 forwards;
}

/*
  animation-fill-mode: forwards
  → element HOLDS the final keyframe state after animation ends
  → without it: element snaps back to original (opacity:0) — visually jarring
*/
```

---

### 📐 Code Task — Card with Lift + Fade-In

```html
<div class="card">
  <h3>Project Alpha</h3>
  <p>A beautifully animated card component.</p>
</div>
```

```css
/* Page load fade-in sequence */
@keyframes fadeInUp {
  from { opacity: 0; transform: translateY(30px); }
  to   { opacity: 1; transform: translateY(0); }
}

.card {
  background: #1e293b;
  border-radius: 16px;
  padding: 2rem;
  max-width: 380px;
  color: #f1f5f9;
  border: 1px solid #334155;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.25);

  /* Runs on page load — no trigger needed */
  animation: fadeInUp 0.6s ease-out forwards;

  /* Responds to hover — trigger required */
  transition: transform 0.3s ease-out,
              box-shadow 0.3s ease-out;
}

.card:hover {
  transform: translateY(-8px);                          /* GPU compositor */
  box-shadow: 0 24px 50px rgba(124, 58, 237, 0.3);    /* colour shadow */
}
```

> ⚡ **GPU Rule:** `transform` and `opacity` are the only two CSS properties that can be animated entirely on the compositor thread — bypassing layout and paint. Animating `width`, `height`, `top`, `left`, or `margin` forces the browser to recalculate the entire layout every frame (16ms budget), causing dropped frames and janky motion.

### 🖼️ Visual Reference
> ![CSS Animations](https://images.unsplash.com/photo-1550745165-9bc0b252726f?w=800&q=80)
> *Unsplash — Smooth UI motion and CSS transition effects in production apps*

---

## 🎯 Q10 · Responsive Web Design

> Responsive design is not optional — it is the baseline. With 60%+ of global web traffic on mobile, a non-responsive site is functionally broken for the majority of real users. This question covers the three pillars of modern responsive CSS.

### 🧩 Key Answers

| Question | Answer |
|----------|--------|
| Mobile-first: `min-width` or `max-width`? | **`min-width`** — start with mobile base, progressively add desktop |
| `@media (prefers-color-scheme: dark)`? | Reads OS-level dark mode preference and applies matching styles |
| Can JavaScript read CSS variables? | ✅ `getComputedStyle(el).getPropertyValue('--var-name')` |
| `var(--color)` vs `var(--color, #fff)`? | Second argument is a **fallback** used if the variable is undefined |

---

### 📐 Part A — Media Queries

```css
/* Syntax */
@media (condition) { /* CSS rules applied when condition is true */ }

/* ─── STANDARD INDUSTRY BREAKPOINTS ─── */

/* Mobile base — no query needed (mobile-first default) */

@media (min-width: 480px)  { /* Large phones  — compact adjustments  */ }
@media (min-width: 768px)  { /* Tablets       — 2-column layouts      */ }
@media (min-width: 1024px) { /* Laptops       — full navigation, sidebar */ }
@media (min-width: 1280px) { /* Desktops      — max-width containers  */ }
@media (min-width: 1536px) { /* Large screens — extended whitespace   */ }
```

---

### 📐 Part B — Mobile-First vs Desktop-First

```
MOBILE-FIRST (✅ Industry Standard)      DESKTOP-FIRST (⚠️ Legacy approach)
────────────────────────────────         ─────────────────────────────────
Base CSS = lean mobile styles            Base CSS = heavy desktop styles
↓                                        ↓
@media (min-width: 768px) {              @media (max-width: 768px) {
  /* ADD tablet features */                /* REMOVE/override for mobile */
}                                        }
↓
@media (min-width: 1024px) {
  /* ADD desktop features */
}

Why mobile-first wins:
✅ 60%+ of traffic is mobile
✅ Forces performance discipline (small CSS first)
✅ Progressive enhancement — add complexity, don't strip it
✅ Google's mobile-first indexing rewards it in search rankings
✅ Smaller CSS payload for the majority of users
```

---

### 📐 Part C — CSS Variables (Custom Properties)

```css
/* ─── DESIGN SYSTEM — defined at :root, available everywhere ─── */
:root {
  /* Color palette */
  --color-bg:        #ffffff;
  --color-surface:   #f8fafc;
  --color-primary:   #7c3aed;
  --color-secondary: #db2777;
  --color-accent:    #f97316;
  --color-text:      #0f172a;
  --color-muted:     #64748b;
  --color-border:    #e2e8f0;

  /* Typography scale */
  --font-size-sm:   0.875rem;
  --font-size-base: 1rem;
  --font-size-lg:   1.25rem;
  --font-size-xl:   clamp(2rem, 4vw, 3.5rem);

  /* Spacing scale */
  --space-xs:  0.5rem;
  --space-sm:  1rem;
  --space-md:  1.5rem;
  --space-lg:  2.5rem;
  --space-xl:  4rem;

  /* Shape & shadow */
  --radius-sm:   6px;
  --radius-md:   12px;
  --radius-lg:   20px;
  --shadow-sm:   0 1px 4px rgba(0,0,0,0.06);
  --shadow-md:   0 4px 24px rgba(0,0,0,0.10);
  --shadow-lg:   0 16px 48px rgba(0,0,0,0.16);
}
```

---

### 📐 Dark Mode — One Block, Zero Extra Code

```css
/* Light = default (:root above) */

/* Dark mode — manual toggle via JS (data-theme="dark") */
[data-theme="dark"] {
  --color-bg:      #0f172a;
  --color-surface: #1e293b;
  --color-text:    #f1f5f9;
  --color-muted:   #94a3b8;
  --color-border:  #334155;
}

/* Dark mode — OS preference (prefers-color-scheme) */
@media (prefers-color-scheme: dark) {
  :root {
    --color-bg:      #0f172a;
    --color-surface: #1e293b;
    --color-text:    #f1f5f9;
    --color-muted:   #94a3b8;
    --color-border:  #334155;
  }
}

/* Components use variables — auto-update in both modes */
body {
  background: var(--color-bg);
  color: var(--color-text);
  transition: background 0.3s ease, color 0.3s ease;
}
```

---

### 📐 Code Task — Full Responsive Design System

```css
/* Mobile-First Responsive Layout */

/* Base — Mobile */
.container {
  width: 100%;
  padding: 0 var(--space-md);
}

.card-grid {
  display: flex;
  flex-direction: column;
  gap: var(--space-md);
}

.card {
  background: var(--color-surface);
  border: 1px solid var(--color-border);
  border-radius: var(--radius-md);
  padding: var(--space-md);
  color: var(--color-text);
  box-shadow: var(--shadow-sm);
}

/* Tablet — 768px+ */
@media (min-width: 768px) {
  .container { padding: 0 var(--space-lg); }

  .card-grid {
    flex-direction: row;
    flex-wrap: wrap;
  }

  .card-grid .card {
    flex: 1 1 calc(50% - var(--space-md));
  }
}

/* Desktop — 1024px+ */
@media (min-width: 1024px) {
  .container {
    max-width: 75rem;
    margin: 0 auto;
  }

  .card-grid .card {
    flex: 1 1 calc(33.333% - var(--space-md));
  }
}
```

> 💡 **Fallback values:** `var(--color-primary, #7c3aed)` — if the variable is undefined or misspelled, the fallback `#7c3aed` is used instead of invisible/broken styling. Always add fallbacks for critical design tokens used in visible properties.

### 🖼️ Visual Reference
> ![Responsive Design](https://images.unsplash.com/photo-1512941937669-90a1b58e7e9c?w=800&q=80)
> *Unsplash — Responsive layout rendering correctly across mobile, tablet, and desktop*

---

<div align="center">

## 📊 Score Card

| # | Topic | Marks |
|:-:|:------|:-----:|
| 01 | CSS Foundations & Methods | **5 / 5** ✅ |
| 02 | Selectors & Targeting | **8 / 8** ✅ |
| 03 | Box Model & Sizing | **7 / 7** ✅ |
| 04 | Color Systems & Opacity | **6 / 6** ✅ |
| 05 | Units & Fluid Typography | **7 / 7** ✅ |
| 06 | Specificity & Cascade | **8 / 8** ✅ |
| 07 | Flexbox Layout System | **10 / 10** ✅ |
| 08 | Pseudo-classes & Elements | **9 / 9** ✅ |
| 09 | Transitions & Animations | **10 / 10** ✅ |
| 10 | Responsive Design System | **10 / 10** ✅ |
| | 🏆 **TOTAL** | **80 / 80** |

<br/>

![CSS3](https://img.shields.io/badge/CSS3-%237c3aed?style=for-the-badge&logo=css3&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-%23db2777?style=for-the-badge&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-%23f97316?style=for-the-badge&logo=javascript&logoColor=white)
![Responsive](https://img.shields.io/badge/Responsive_Design-%2306b6d4?style=for-the-badge)
![Dark Mode](https://img.shields.io/badge/Dark_Mode_Ready-%237c3aed?style=for-the-badge)

<br/>

---

---

<div align="center">
<img src="./footer.svg" width="100%" alt="Footer"/>
</div>

</div>
