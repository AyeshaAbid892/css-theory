<div align="center">
<img src="./header.svg" width="100%" alt="CSS Theory Assignment"/>
</div>

<br/>
<div align="center"> 

# 🌐 CSS Theoretical Questions
### 📖 A Complete Reference Guide with Code Examples & Visual References 🖼️

![Subject](https://img.shields.io/badge/Subject-CSS_Theory-4f9ef8?style=for-the-badge)
![Questions](https://img.shields.io/badge/Questions-10_Total-10b981?style=for-the-badge)
![Level](https://img.shields.io/badge/Level-Core-f59e0b?style=for-the-badge)
![Repo](https://img.shields.io/badge/Repo-css--theory-7c3aed?style=for-the-badge)

---


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

## 〔 🟢 BEGINNER · Q1 — Q5 〕

</div>

</div>


## `🎯 Question 1 `

## **What is CSS and how do you add it to an HTML page?**

> **CSS (Cascading Style Sheets)** is the styling language of the web. It separates visual presentation from HTML structure, giving developers precise control over layout, color, typography, spacing, and animation. Without CSS, every webpage is an unstyled wall of text.

---

## 🛠️ What Problem Does CSS Solve?
>Before CSS, layout and styling were mixed inside HTML tags (like `<font>` or `bgcolor`), making code messy and hard to maintain. CSS solves this by introducing **Separation of Concerns (SoC)**, allowing developers to manage structure (HTML) and presentation (CSS) completely separately.

## 🧩 Keyword Concepts

| Keyword | Meaning |
| :--- | :--- |
| **Cascading** | Styles flow from parent → child; later rules can override earlier ones. |
| **Separation of Concerns** | HTML handles structure, CSS handles presentation, and JS handles behaviour. |
| **Render Engine** | The browser parses CSS and paints pixels based on computed styles. |
| **Specificity** | The scoring system that decides which rule wins when two conflict. |

---

##  3. 📐 Three Methods of Adding CSS (With Code Tasks)

## ①Method A: <br>
#### External CSS — `<link>` tag ✅ `(Industry Standard)`

>Links an isolated text asset containing style definitions directly to an HTML file using a `<link>` structural wrapper element within the document `<head>`.

```html
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>External CSS Example</title>
    <link rel="stylesheet" href="styles.css" />
</head>
<body>
    <h1>Hello World</h1>
</body>
</html>
```

```css
/* styles.css */
/* styles.css */
body {
    font-family: 'Segoe UI', sans-serif;
    background-color: #0f172a;
    color: #f1f5f9;
    margin: 0;
}
```

## ② Method B: <br>

#### Internal CSS — `<style>` block ⚠️ `(Single-page Only)`

>Embeds explicit declaration blocks within a scoped `<style>` element placed inside the document's `<head>`.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Internal CSS Example</title>
    <style>
        h1 {
            color: #7c3aed;
            font-size: 2rem;
        }
    </style>
</head>
<body>
    <h1>Hello World</h1>
</body>
</html>
```

## ③ Method C: <br>
#### Inline CSS  — `style=""` attribute ❌ `(Avoid in Production)`

>Injects key-value presentation declarations directly into an individual HTML tag using the native global `style` attribute wrapper.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Inline CSS Example</title>
</head>
<body>
    <p style="color: #db2777; font-size: 14px;">Avoid this in real projects.</p>
</body>
</html>
```

---

## 🏆 Method Comparison

| Criterion | External ✅ | Internal ⚠️ | Inline ❌ |
|-----------|:-----------:|:-----------:|:--------:|
| Reusable across pages | ✅ | ❌ | ❌ |
| Browser caches the file | ✅ | ❌ | ❌ |
| Clean HTML structure | ✅ | ⚠️ | ❌ |
| Team-friendly | ✅ | ⚠️ | ❌ |
| Overrides everything | — | — | ✅ (bad) |

## **📌 Recommended Method for Real Projects::** <br>
>`External CSS` is highly recommended for production/real-world projects because it ensures complete separation of concerns, enables browser caching to improve performance, and keeps the code maintainable for engineering teams.

## **🛠️ Why External CSS is Preferred Over Inline CSS:** <br>
><br>1.`Browser Cache Optimization:` The client browser downloads an external .css asset file exactly once. It caches this layout layer locally across subsequent navigation patterns, removing the need to fetch repetitive design logic on every new page view. Inline styles bloat every document payload with duplicate, uncacheable bytes.<br>
2.`Specificity & Cascade Control:` Inline styles inject rules directly at the highest standard priority tier inside the browser engine's cascade calculations, carrying a crushing specificity weight score of 1000 points. This heavy footprint makes targeting global modifications via stylesheets incredibly difficult without writing messy, anti-pattern overrides like !important.<br>
3.`Developer Ergonomics and Team Scalability:` Separating styling logic from structural code allows engineering teams to modify layout assets concurrently without tripping over merge conflicts in core HTML views or application route templates.

## `🖼️ Visual Reference`

<img width="1408" height="600" alt="Gemini_Generated_Image_ytgm9oytgm9oytgm" src="https://github.com/user-attachments/assets/a2795b3c-9ae4-4914-88ec-a8b7adb75afa" />


---

## `🎯 Question 2 `

## **Explain CSS Selectors with examples?**

> **CSS Selectors** are targeting patterns that tell the browser's render engine exactly which HTML element(s) to apply styles to. Every CSS ruleset begins with a selector, mapping visual declarations to structural nodes in the `DOM tree`.

---

## 🧩 Key Concepts & Core Answers

| Question | Technical Answer |
| :--- | :--- |
| **Class vs ID — Highest Specificity?** | **ID Selector** has a significantly higher weight score (**100 points**) compared to a Class Selector (**10 points**). |
| **Direct Child vs Any Descendant?** | **Child (`>`)** only targets elements exactly one level down. **Descendant (space)** targets matching elements at any nesting depth. |
| **Same Class on multiple elements?** | ✅ **Yes**. Classes are explicitly designed to be reusable utility blueprints. |
| **Same ID on multiple elements?** | ❌ **No**. The HTML specification mandates that an ID must be unique per document. |

---

## 📐 All 7 Selector Types (With Valid HTML & CSS Implementation)

### **1. Universal Selector `(*)`**

> Targets every single element globally within the DOM tree. It is primarily used by engineers to overwrite default browser agent stylesheets and establish a unified baseline padding, margin, and box-sizing constraint.

```html
<!-- index.html -->
<main>
  <div>
    <section>Global Reset Layout Matrix</section>
  </div>
</main>
```

```css
/* styles.css */
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
```

---
### **2. Element / Type Selector `(element)`**

> Matches and updates all structural nodes matching that exact HTML tag configuration across the entire document layer

```html
<!-- index.html -->
<p>This structural node will receive standard typography mapping.</p>
<p>Every subsequent paragraph shares this identical presentation blueprint.</p>
```

```css
/* styles.css */
p {
  font-size: 1rem;
  line-height: 1.7;
  color: #334155;
}
```

---

### **3. Class Selector `(.class)`**

> Targets any element carrying the matching global `class` attribute. It is highly reusable and serves as the fundamental building block for modular `Component-Driven Development (CDD)`.

```html
<!-- index.html -->
<div class="card">Modular Component Interface A</div>
<div class="card">Modular Component Interface B</div>
```

```css
/* styles.css */
.card {
  background: #1e293b;
  border-radius: 12px;
  padding: 1.5rem;
  border: 1px solid #334155;
}
```

---

### **4. ID Selector `(#id)`**

> Targets a solitary, entirely unique structural identifier inside the document scope. The HTML ecosystem strictly enforces that no two active nodes can share the same ID token.

```html
<!-- index.html -->
<section id="hero">Unique Landmark Viewport Hook</section>
```

```css
/* styles.css */
#hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}
```

---

### **5. Grouping Selector `(comma separated)`**

> Aggregates distinct targeting configurations to share a unified block of declaration properties. This directly implements the DRY (Don't Repeat Yourself) architectural principle to keep stylesheet payloads minimal.

```html
<!-- index.html -->
<h1>Main Document Title</h1>
<h2>Section Sub-Header Node</h2>
```

```css
/* styles.css */
h1, h2, h3, h4 {
  font-family: 'Georgia', serif;
  color: #7c3aed;
  margin-bottom: 0.75rem;
}
```

---

### **6. Descendant Selector `(space combinator)`**

> Recursively matches any target element nested anywhere deeper within the specified structural parent node boundary, traversing down infinite levels of the` DOM hierarchy tree`.

```html
<!-- index.html -->
<div class="card">
  <article>
    <p>This nested content is a deep descendant node of the card wrapper.</p>
  </article>
</div>
```

```css
/* styles.css */
.card p {
  color: #94a3b8;
  font-size: 0.95rem;
}
```

---

### **7. Child Selector `(> combinator)`**

> Strictly matches elements that exist exactly one branch step down from the direct parent container node. It deliberately ignores grandchildren or any element locked inside deeper nested layers.

```html
<!-- index.html -->
<ul class="parent-list">
  <li>Direct Child Node (This element will be styled)</li>
  <li>
    <div>
      <p>Nested Grandchild Node (Explicitly ignored by the child selector)</p>
    </div>
  </li>
</ul>
```

```css
/* styles.css */
.parent-list > li {
  padding: 0.5rem 0;
  border-bottom: 1px solid #e2e8f0;
}
```

---
## 🆚 Class vs ID — Architectural Decision Rule

>From a modern software architecture perspective, your usage rule should be clear, strict, and driven by semantic specifications:

### **1. When to use a Class `(.blueprint)` — Reusable Elements**

> Classes are explicitly designed to be dynamic blueprints reused across multiple elements on a single page or throughout an entire application stack. Even if an element appears only once on a view right now (like a primary button), you should still declare it as a class if it conceptually represents a shareable interface element.

```html
<!-- index.html -->
<button class="btn-primary">Submit Form</button>
<button class="btn-primary">Cancel Operation</button>
```

```css
/* styles.css */
.btn-primary {
  background: #7c3aed;
  color: #ffffff;
  padding: 0.75rem 1.5rem;
  border-radius: 8px;
  cursor: pointer;
}
```

### **2. When to use an ID `(#landmark)` — Unique Identifiers**

> The HTML specification strictly mandates that an ID must be completely unique within the document scope. You must never use the same ID on multiple elements, as it violates semantic rules and breaks JavaScript integrations. Reserve IDs exclusively as functional hooks for client-side scripts, anchor layout links `(href="#main-content")`, or globally unique interface structural wrappers.

```html
<!-- index.html -->
<nav id="main-nav">
  </nav>
```

```css
/* styles.css */
#main-nav {
  position: sticky;
  top: 0;
  z-index: 999;
  background: #0f172a;
}
```

## **💡 Core Architectural Rule:** <br>
>Default to classes for `99%` of your styling tasks. Avoid using IDs inside your stylesheets because their extremely high weight score inside the Specificity Hierarchy disrupts the natural cascade ecosystem, making global project updates and code maintenance difficult.

## `🖼️ Visual Reference`

<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/d74a572a-32c2-4c36-ab7b-652fe953ba84" />


---

## `🎯 Question 3  `

## **CSS Box Model**

> Every HTML element parsed by the browser's render engine is modeled as a structured **rectangular box**. The CSS Box Model is the foundational specification that dictates exactly how an element's spatial dimensions, internal breathing room, and external boundaries are calculated and rendered.

---

## 🧩 Key Concepts & Core Answers

| Requirement Check | Technical Layout Answer |
| :--- | :--- |
| **Which layer is the innermost?** | **Content Layer** — The core dimensional nucleus where the element's raw text, images, or child nodes reside. |
| **Is padding inside or outside the border?** | **Inside** — Padding is the internal structural clearing located between the content node and the border boundary, absorbing the element's background color. |
| **What does `margin: 0 auto` do to a block element?** | Sets the vertical margins to `0` and dynamically calculates equal horizontal spacing, centering the block element inside its parent container. |
| **With `border-box`, does width include padding?** | ✅ **Yes**. The calculated layout width is immutable; it automatically incorporates `width = content + padding + border`. |

---

## 📐 The Four Layers — Structural Descriptions


#### 1. Content Layer
>* **Role:** The innermost nucleus of the box.
>* **Control:** It directly houses the native node payloads such as typography strings, multimedia assets, or nested child elements. Under standard rules, its dimensions are manipulated via the `width` and `height` properties.

#### 2. Padding Layer (Internal Clearance)
>* **Role:** The internal breathing room of the component.
>* **Control:** It creates defensive padding space between the core text content and the outer structural frame. Because it sits inside the perimeter, it dynamically displays the element's background color or linear gradients.

#### 3. Border Layer (Structural Frame)
>* **Role:** The visible boundary outline of the element box.
>* **Control:** It serves as a visual separator wrapping the content and padding layers. It is configurable via thickness values, style choices (`solid`, `dashed`), and paint colors.

#### 4. Margin Layer (External Separation)
>* **Role:** The outermost defensive shield.
>* **Control:** It generates empty, entirely transparent buffer space between the current element and neighboring nodes on the page. Margins never absorb background elements and are utilized to control global component stacking behavior.

---

## 📐 Structural Comparison Matrix

| Layer Parameter | Control Scope | Transparent Constraints |
| :--- | :--- | :---: |
| **Content** | Primary structural node payload | Dependent on children |
| **Padding** | Inner spatial defensive buffer | ❌ Inherits background styles |
| **Border** | Visible peripheral frame mapping | ❌ Rendered vector line |
| **Margin** | External separation boundaries | ✅ Always Transparent |

---

---

## 📐 The Four Layers — Visualised

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

##  🆚 Box Sizing: `content-box` vs `border-box` (The Layout Math)

#### 1. Legacy Approach: `content-box` (The Anti-Pattern)<br>
>Under this default specification model, the browser maps the assigned width property directly to the inner content layer only. When you add padding and borders, the element expands outward dynamically, inflating the actual rendered footprint on the viewport and breaking responsive grid systems.

```css
/* ❌ Mathematical Redundancy & Formula:
   Total Rendered Outer Width = 300px (width) + 40px (paddings) + 4px (borders) = 344px on screen.
   (External margin adds an additional 16px buffer boundary around this inflated container). */
.legacy-box {
  box-sizing: content-box;
  width: 300px;
  padding: 20px;
  border: 2px solid #7c3aed;
  margin: 16px;
}

```

#### 2. Production Approach: border-box (The Professional Code Task Standard)<br>
>This modern layout architecture forces the browser's visual render engine to treat the assigned width property as the final, immutable outer constraint of the box footprint. If padding or borders are scaled up, the content nucleus automatically contracts inward to maintain structural compliance perfectly.

```css
/* ✅ Fluid Layout Architecture Formula:
   Total Rendered Outer Width = Exactly 300px constraint on screen.
   The browser layout subsystem automatically shrinks the inner content core down to 256px (300 - 40 - 4) to absorb internal clearance spacing safely. */
.box {
  box-sizing: border-box;
  width: 300px;
  padding: 20px;
  border: 2px solid #7c3aed;
  margin: 16px;
}

```
#### 🏆 Architectural Industry Standard Verdict<br>
>In enterprise-level web design, `border-box` is globally mandatory. Modern fluid layouts, multi-device interfaces, and dynamic components cannot scale reliably if local paddings continuously expand container footprints.<br>
To eliminate mathematical redundancy entirely across a project codebase, software engineers execute a global unified box-sizing reset strategy that targets both native layout blocks and pseudo-elements:

```css
/* Universal Pseudo-Elements Reset Strategy applied across enterprise applications */
*, 
*::before, 
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

```

## `🖼️ Visual Reference`

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/8a37d696-5563-4e66-b64d-ae653eca7923" />


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
