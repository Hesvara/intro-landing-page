# Hesvara Design Specification

> Complete design reference for rebuilding the Hesvara site as pure static HTML/CSS.
> Extracted from 5 pages: `index.html`, `about.html`, `beta.html`, `invite.html`, `privacy.html`.

---

## 1. Color Palette

### CSS Custom Properties (Brand Colors)

| Variable             | Hex       | Role                                                      |
|----------------------|-----------|------------------------------------------------------------|
| `--evergreen`        | `#2E5A45` | Primary brand — CTA backgrounds, active nav, solution accents, checkmarks |
| `--deep-forest`      | `#1F3A2E` | Primary dark — Logo color, headings, hover state for primary buttons |
| `--slate-ink`        | `#2C3A4B` | Secondary — Nav links, secondary button border/text, problem card accents |
| `--brass`            | `#B08B3E` | Accent — List bullets (privacy page), invite badge, bio bullets, notice border |
| `--airy`             | `#FAF9F5` | Background light — Body gradient start, mobile nav bg, button text on primary |
| `--gradient-off-white` | `#F5F3ED` | Background end — Body gradient end                        |
| `--soft-neutral`     | `#E8E6DC` | Borders — Section dividers, mobile nav bottom border, team link bg |
| `--secondary-text`   | `#6F6D66` | Muted text — Footer text, descriptions, stat labels, attribution |
| `--ink`              | `#1B1F23` | Body text — Default text color, form input text            |

### Derived / Inline Colors

| Value                              | Usage                                                   |
|-------------------------------------|---------------------------------------------------------|
| `rgba(46, 90, 69, 0.04)`           | Background decoration radial gradients                  |
| `rgba(46, 90, 69, 0.05)`           | Solution card background, value-column.get bg           |
| `rgba(46, 90, 69, 0.08)`           | Status badge background, success icon bg (invite)       |
| `rgba(46, 90, 69, 0.1)`            | Card borders, benefit-item borders, feature-item borders |
| `rgba(46, 90, 69, 0.12)`           | Content-card border, trust-bar border                   |
| `rgba(46, 90, 69, 0.15)`           | Solution card border, join-section border, form-card border |
| `rgba(46, 90, 69, 0.2)`            | Status badge border, form input border                  |
| `rgba(46, 90, 69, 0.25)`           | Hover card border, CTA hover shadow                     |
| `rgba(44, 58, 75, 0.04)`           | Background decoration (slate variant)                   |
| `rgba(44, 58, 75, 0.05)`           | Problem card background, value-column.ask bg            |
| `rgba(44, 58, 75, 0.15)`           | Problem card border, value-column.ask border            |
| `rgba(44, 58, 75, 0.2)`            | Secondary button/sign-in hover shadow                   |
| `rgba(255, 255, 255, 0.5)`         | Benefit-item bg, feature-item bg, stat-card bg          |
| `rgba(255, 255, 255, 0.6)`         | Feature-card bg, component-card bg, trust-bar bg        |
| `rgba(255, 255, 255, 0.65)`        | Content-card bg, team-card bg, notice-box bg            |
| `rgba(255, 255, 255, 0.7)`         | Join-section bg, form-card bg, CTA section bg, benefit hover bg |
| `rgba(255, 255, 255, 0.85)`        | Stack-card bg (beta hero)                               |
| `rgba(176, 139, 62, 0.07)`         | Invite badge background                                 |
| `rgba(176, 139, 62, 0.18)`         | Invite badge border                                     |
| `rgba(0, 0, 0, 0.08)`              | Card hover shadow, mobile nav shadow, stack-card shadow |
| `white` / `#FFFFFF`                | Form input bg, secondary button hover text, nav-signin hover text |

### Error State Colors

| Value      | Usage                          |
|------------|--------------------------------|
| `#fef2f2`  | Form error background          |
| `#fecaca`  | Form error border              |
| `#991b1b`  | Form error text                |
| `#c0392b`  | Invite page inline error text  |

### Gradients

```css
/* Body background */
background: linear-gradient(135deg, #FAF9F5 0%, #F5F3ED 100%);

/* Feature card hover accent line */
background: linear-gradient(90deg, #2E5A45, #2C3A4B);
```

---

## 2. Typography

### Font Import

```css
@import url('https://fonts.googleapis.com/css2?family=Crimson+Pro:wght@300;400;600&family=Source+Sans+3:wght@400;600;700&display=swap');
```

Or as a `<link>` tag (used in `invite.html`):
```html
<link href="https://fonts.googleapis.com/css2?family=Crimson+Pro:wght@300;400;600&family=Source+Sans+3:wght@400;600;700&display=swap" rel="stylesheet">
```

### Font Families

| Role      | Stack                                        |
|-----------|----------------------------------------------|
| Headings  | `'Crimson Pro', Georgia, serif`              |
| Body/UI   | `'Source Sans 3', Arial, sans-serif`         |

### Type Scale

| Element                     | Family       | Size                              | Weight | Line-height | Letter-spacing | Color               |
|-----------------------------|--------------|-----------------------------------|--------|-------------|----------------|----------------------|
| **H1 (index hero)**         | Crimson Pro  | `clamp(2.75rem, 7vw, 4.5rem)`    | 300    | 1.1         | -1px           | `--deep-forest`      |
| **H1 .highlight**           | Crimson Pro  | (inherited)                       | 600    | (inherited) | (inherited)    | `--evergreen`        |
| **H1 (about/privacy page)** | Crimson Pro  | `clamp(2.5rem, 6vw, 3.5rem)`     | 300    | 1.15        | -0.5px         | `--deep-forest`      |
| **H1 (beta hero)**          | Crimson Pro  | `clamp(2rem, 4.5vw, 2.75rem)`    | 300    | 1.2         | -0.5px         | `--deep-forest`      |
| **H1 (invite)**             | Crimson Pro  | `38px`                            | 300    | 1.12        | —              | `--deep-forest`      |
| **H2 (section header)**     | Crimson Pro  | `clamp(1.75rem, 4vw, 2.5rem)`    | 400    | —           | -0.5px         | `--deep-forest`      |
| **H2 (section body)**       | Source Sans  | `1.6rem`                          | 700    | —           | —              | `--deep-forest`      |
| **H2 (join-section)**       | Crimson Pro  | `2.25rem`                         | 400    | —           | —              | `--deep-forest`      |
| **H2 (CTA section)**        | Crimson Pro  | `2rem`                            | 400    | —           | —              | `--deep-forest`      |
| **H3 (feature-card)**       | Source Sans  | `1.25rem`                         | 700    | —           | —              | `--deep-forest`      |
| **H3 (problem/solution)**   | Source Sans  | `1.35rem`                         | 700    | —           | —              | varies               |
| **H3 (form success)**       | Crimson Pro  | `1.75rem`                         | 400    | —           | —              | `--deep-forest`      |
| **H3 (section, privacy)**   | Source Sans  | `1.15rem`                         | 700    | —           | —              | `--ink`              |
| **H4 (feature-content)**    | Source Sans  | `1rem`                            | 700    | —           | —              | `--deep-forest`      |
| **H4 (status-item)**        | Source Sans  | `0.85rem`                         | 700    | —           | 0.5px          | `--secondary-text`   |
| **Body text**               | Source Sans  | base (1rem / 16px implied)        | 400    | 1.6         | —              | `--ink`              |
| **Subtitle (hero)**         | Source Sans  | `clamp(1.05rem, 2.2vw, 1.25rem)` | 400    | 1.75        | —              | `--ink` @ 0.9 opacity |
| **Lead text (about/priv)**  | Source Sans  | `1.15rem`                         | 400    | 1.75        | —              | `--ink` @ 0.9 opacity |
| **Section paragraph**       | Source Sans  | `1.05rem`                         | 400    | 1.7 or 1.75 | —              | `--secondary-text` or `--ink` |
| **Card description**        | Source Sans  | `0.95rem`                         | 400    | 1.6         | —              | `--ink` @ 0.85 opacity |
| **Tagline**                 | Source Sans  | `0.9rem`                          | 700    | —           | 2px            | `--slate-ink`, uppercase |
| **Nav link**                | Source Sans  | `0.95rem`                         | 600    | —           | 0.3px          | `--slate-ink`        |
| **Nav CTA**                 | Source Sans  | `0.9rem`                          | 600    | —           | 0.3px          | `--airy`             |
| **Nav sign-in**             | Source Sans  | `0.9rem`                          | 600    | —           | 0.3px          | `--slate-ink`        |
| **Logo**                    | Crimson Pro  | `2rem`                            | 300    | —           | 0.5px          | `--deep-forest`      |
| **Primary button**          | Source Sans  | `1rem`                            | 600    | —           | 0.3px          | `--airy`             |
| **Secondary button**        | Source Sans  | `1rem`                            | 600    | —           | 0.3px          | `--slate-ink`        |
| **Submit button**           | Source Sans  | `1.05rem`                         | 600    | —           | 0.3px          | `white`              |
| **Form label**              | Source Sans  | `0.9rem`                          | 600    | —           | 0.2px          | `--slate-ink`        |
| **Form input**              | Source Sans  | `1rem`                            | 400    | —           | —              | `--ink`              |
| **Status badge**            | Source Sans  | `0.8rem`                          | 600    | —           | 0.5px          | `--evergreen`        |
| **Privacy note**            | Source Sans  | `0.85rem`                         | 400    | 1.5         | —              | `--secondary-text`   |
| **Footer text**             | Source Sans  | `0.9rem`                          | 400    | —           | —              | `--secondary-text`   |
| **Footer links**            | Source Sans  | `0.9rem`                          | 400    | —           | —              | `--slate-ink`        |
| **Copyright line**          | Source Sans  | `0.85rem`                         | 400    | —           | —              | `--secondary-text`   |
| **Stat number**             | Crimson Pro  | `2.5rem`                          | 600    | —           | —              | `--evergreen`        |
| **Stat label**              | Source Sans  | `0.9rem`                          | 400    | 1.4         | —              | `--secondary-text`   |
| **Invite badge**            | Source Sans  | `12px`                            | 700    | —           | 1.2px          | `--brass`, uppercase |
| **Invite intro**            | Source Sans  | `17px`                            | 400    | 1.7         | —              | `--secondary-text`   |

---

## 3. Spacing & Layout

### Container Max-Widths

| Page              | `max-width` | Padding              |
|-------------------|-------------|----------------------|
| index.html        | `1200px`    | `3rem 5% 5rem`       |
| beta.html         | `1100px`    | `3rem 5% 5rem`       |
| about.html        | `1000px`    | `3rem 5% 5rem`       |
| privacy.html      | `1000px`    | `3rem 5% 5rem`       |
| invite.html       | `640px`     | `40px 32px 60px`     |

All containers use `margin: 0 auto` for centering and `position: relative; z-index: 1`.

### Section Spacing

| Section type          | `margin-bottom` | Internal padding |
|-----------------------|-----------------|------------------|
| Hero                  | `5rem`          | —                |
| Product overview      | `5rem`          | —                |
| Problem/solution      | `5rem`          | —                |
| Benefits              | `5rem`          | —                |
| Value exchange (beta) | `5rem`          | —                |
| Components (beta)     | `5rem`          | —                |
| Section (about/priv)  | `4rem`          | —                |
| Section header        | —               | `margin-bottom: 3rem` (index), `2.5rem` (beta) |
| Page header           | —               | `margin-bottom: 4rem` |
| Join section          | —               | `3.5rem 2.5rem`  |
| CTA section           | —               | `3rem 2.5rem`    |
| Content card          | —               | `2.5rem`         |

### Card Grids

| Grid                    | Columns                                     | Gap       | Notes                   |
|-------------------------|----------------------------------------------|-----------|--------------------------|
| Features (index)        | `repeat(auto-fit, minmax(280px, 1fr))`       | `1.75rem` | 5 cards, wraps naturally |
| Components (beta)       | `repeat(auto-fit, minmax(240px, 1fr))`       | `1.75rem` | 4 cards                  |
| Benefits (index)        | `repeat(auto-fit, minmax(280px, 1fr))`       | `1.25rem` | max-width: 950px         |
| Problem/solution        | `1fr 1fr`                                    | `2rem`    | Fixed 2-column           |
| Value grid (beta)       | `1fr 1fr`                                    | `2rem`    | Fixed 2-column           |
| Feature list (about)    | `repeat(2, 1fr)`                             | `1.25rem` | Fixed 2-column           |
| Stat grid (about)       | `repeat(3, 1fr)`                             | `1.5rem`  | Fixed 3-column           |
| Status grid (about)     | `repeat(2, 1fr)`                             | `1.25rem` | Fixed 2-column           |
| Form row                | `1fr 1fr`                                    | `1rem`    | First/last name side-by-side |
| Team card (about)       | `1fr 2fr`                                    | `2.5rem`  | Photo : bio ratio        |
| Hero (beta)             | `1fr 1fr`                                    | `3rem`    | Text : cards             |
| Details (invite)        | `1fr 1fr 1fr`                                | `16px`    | 3 detail cards           |

### Header & Footer

| Element      | Padding             | Notes                          |
|--------------|---------------------|--------------------------------|
| Header       | `1.5rem 5%`         | `1.25rem 5%` at 768px          |
| Footer       | `3rem 5% 2rem`      | Centered text                  |
| Invite nav   | `24px 40px`         | Simplified single-logo nav     |
| Invite footer| `24px 32px 40px`    | Centered, max-width: 640px     |

---

## 4. Components

### 4.1 Navigation Bar

```css
.header {
    position: relative;
    z-index: 10;
    padding: 1.5rem 5%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    opacity: 0;
    animation: fadeInDown 0.8s ease forwards;
}

.logo {
    font-family: 'Crimson Pro', Georgia, serif;
    font-size: 2rem;
    font-weight: 300;
    color: #1F3A2E;
    letter-spacing: 0.5px;
    text-decoration: none;
}

.nav {
    display: flex;
    align-items: center;
    gap: 2rem;
}

.nav-link {
    font-size: 0.95rem;
    font-weight: 600;
    color: #2C3A4B;
    text-decoration: none;
    transition: color 0.3s ease;
    letter-spacing: 0.3px;
}
.nav-link:hover,
.nav-link.active {
    color: #2E5A45;
}

.nav-cta {
    padding: 0.6rem 1.5rem;
    background: #2E5A45;
    color: #FAF9F5;
    border-radius: 50px;
    font-size: 0.9rem;
    font-weight: 600;
    text-decoration: none;
    transition: all 0.3s ease;
    letter-spacing: 0.3px;
}
.nav-cta:hover {
    background: #1F3A2E;
    transform: translateY(-2px);
    box-shadow: 0 6px 16px rgba(46, 90, 69, 0.25);
}
.nav-cta.active {
    background: #1F3A2E;
}

.nav-signin {
    display: inline-block;
    padding: 0.5rem 1.25rem;
    font-family: 'Source Sans 3', Arial, sans-serif;
    font-size: 0.9rem;
    font-weight: 600;
    background: transparent;
    color: #2C3A4B;
    border: 2px solid #2C3A4B;
    border-radius: 50px;
    text-decoration: none;
    transition: all 0.3s ease;
    letter-spacing: 0.3px;
}
.nav-signin:hover {
    background: #2C3A4B;
    color: white;
    transform: translateY(-2px);
    box-shadow: 0 6px 16px rgba(44, 58, 75, 0.2);
}
```

**Mobile hamburger menu** (3 horizontal bars, CSS-only X animation):

```css
.mobile-menu-toggle {
    display: none;          /* shown at 768px */
    background: none;
    border: none;
    cursor: pointer;
    padding: 0.5rem;
}
.mobile-menu-toggle span {
    display: block;
    width: 24px;
    height: 2px;
    background: #2C3A4B;
    margin: 5px 0;
    transition: all 0.3s ease;
}

/* X animation when active */
.mobile-menu-toggle.active span:nth-child(1) {
    transform: rotate(45deg) translate(5px, 5px);
}
.mobile-menu-toggle.active span:nth-child(2) {
    opacity: 0;
}
.mobile-menu-toggle.active span:nth-child(3) {
    transform: rotate(-45deg) translate(5px, -5px);
}
```

**Nav structure** (identical across index, about, beta, privacy):
- Home | About | Privacy | View Demo | [Join Beta] (pill CTA) | [Sign In] (outlined pill)

**Invite page** uses a simplified single-logo nav with no links.

---

### 4.2 Hero Section

**Index — Centered text hero:**

```css
.hero {
    text-align: center;
    margin-bottom: 5rem;
    opacity: 0;
    animation: fadeInUp 1s ease 0.3s forwards;
}

.tagline {
    font-size: 0.9rem;
    font-weight: 700;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: #2C3A4B;
    margin-bottom: 1.25rem;
}

h1 {
    font-family: 'Crimson Pro', Georgia, serif;
    font-size: clamp(2.75rem, 7vw, 4.5rem);
    font-weight: 300;
    line-height: 1.1;
    color: #1F3A2E;
    margin-bottom: 1.75rem;
    letter-spacing: -1px;
}
h1 .highlight {
    font-weight: 600;
    color: #2E5A45;
    display: block;
}

.subtitle {
    font-size: clamp(1.05rem, 2.2vw, 1.25rem);
    color: #1B1F23;
    max-width: 680px;
    margin: 0 auto 2rem;
    line-height: 1.75;
    opacity: 0.9;
}

.hero-buttons {
    display: flex;
    gap: 1rem;
    justify-content: center;
    flex-wrap: wrap;
    margin-bottom: 2rem;
}
```

**Beta — 2-column hero with card stack:**

```css
.hero {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 3rem;
    align-items: center;
    margin-bottom: 5rem;
    opacity: 0;
    animation: fadeInUp 1s ease 0.3s forwards;
}
```

Left column: text content. Right column: `.card-stack` with 3 absolutely positioned, rotated cards:

```css
.card-stack {
    position: relative;
    height: 320px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.stack-card {
    position: absolute;
    width: 240px;
    padding: 1.5rem;
    background: rgba(255, 255, 255, 0.85);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(46, 90, 69, 0.15);
    border-radius: 12px;
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.08);
    transition: transform 0.4s ease;
}
.stack-card:nth-child(1) { transform: rotate(-6deg) translate(-20px, 10px); z-index: 1; }
.stack-card:nth-child(2) { transform: rotate(0deg) translate(0, -10px);     z-index: 2; }
.stack-card:nth-child(3) { transform: rotate(5deg) translate(20px, 15px);   z-index: 1; }
```

---

### 4.3 Feature / Component Cards (Glass-morphism)

Used for features (index) and components (beta):

```css
.feature-card {
    padding: 2.25rem 2rem;
    background: rgba(255, 255, 255, 0.6);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(46, 90, 69, 0.1);
    border-radius: 12px;
    transition: all 0.4s ease;
    position: relative;
    overflow: hidden;
}

/* Animated top accent line on hover */
.feature-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 3px;
    background: linear-gradient(90deg, #2E5A45, #2C3A4B);
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.4s ease;
}

.feature-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 16px 32px rgba(0, 0, 0, 0.08);
    border-color: rgba(46, 90, 69, 0.25);
}
.feature-card:hover::before {
    transform: scaleX(1);
}

.feature-icon {
    font-size: 1.75rem;
    margin-bottom: 0.85rem;
    display: block;
}

.feature-card h3 {
    font-size: 1.25rem;
    font-weight: 700;
    color: #1F3A2E;
    margin-bottom: 0.65rem;
}

.feature-card p {
    font-size: 0.95rem;
    color: #1B1F23;
    opacity: 0.85;
    line-height: 1.6;
}
```

---

### 4.4 Problem / Solution Grid

```css
.problem-solution-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
}

.problem-card, .solution-card {
    padding: 2.5rem;
    border-radius: 12px;
}

.problem-card {
    background: rgba(44, 58, 75, 0.05);
    border: 1px solid rgba(44, 58, 75, 0.15);
}
.solution-card {
    background: rgba(46, 90, 69, 0.05);
    border: 1px solid rgba(46, 90, 69, 0.15);
}

/* List items — no bullet, uses ::before pseudo */
.problem-card li::before {
    content: "\2717";      /* ✗ */
    color: #2C3A4B;
    font-weight: 700;
}
.solution-card li::before {
    content: "\2713";      /* ✓ */
    color: #2E5A45;
    font-weight: 700;
}
```

---

### 4.5 Benefits Grid

```css
.benefits-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.25rem;
    max-width: 950px;
    margin: 0 auto;
    text-align: left;
}

.benefit-item {
    display: flex;
    align-items: flex-start;
    gap: 0.85rem;
    padding: 1.15rem;
    background: rgba(255, 255, 255, 0.5);
    backdrop-filter: blur(5px);
    border-radius: 8px;
    border: 1px solid rgba(46, 90, 69, 0.1);
    transition: all 0.3s ease;
}
.benefit-item:hover {
    background: rgba(255, 255, 255, 0.7);
    border-color: rgba(46, 90, 69, 0.2);
    transform: translateX(4px);
}

.benefit-icon {
    font-size: 1.35rem;
    flex-shrink: 0;
    margin-top: 0.1rem;
}
.benefit-text {
    font-size: 0.95rem;
    color: #1B1F23;
    opacity: 0.9;
    line-height: 1.55;
}
```

---

### 4.6 CTA Buttons

**Primary (filled):**

```css
.primary-button {
    display: inline-block;
    padding: 0.95rem 2.25rem;
    font-family: 'Source Sans 3', Arial, sans-serif;
    font-size: 1rem;
    font-weight: 600;
    background: #2E5A45;
    color: #FAF9F5;
    border: 2px solid #2E5A45;
    border-radius: 50px;
    text-decoration: none;
    transition: all 0.3s ease;
    letter-spacing: 0.3px;
}
.primary-button:hover {
    background: #1F3A2E;
    border-color: #1F3A2E;
    transform: translateY(-2px);
    box-shadow: 0 10px 25px rgba(46, 90, 69, 0.25);
}
```

**Secondary (outlined):**

```css
.secondary-button {
    display: inline-block;
    padding: 0.95rem 2.25rem;
    font-family: 'Source Sans 3', Arial, sans-serif;
    font-size: 1rem;
    font-weight: 600;
    background: transparent;
    color: #2C3A4B;
    border: 2px solid #2C3A4B;
    border-radius: 50px;
    text-decoration: none;
    transition: all 0.3s ease;
    letter-spacing: 0.3px;
}
.secondary-button:hover {
    background: #2C3A4B;
    color: white;
    transform: translateY(-2px);
    box-shadow: 0 8px 20px rgba(44, 58, 75, 0.2);
}
```

**Submit button (full-width):**

```css
.join-submit, .form-submit {
    width: 100%;
    padding: 1rem 2rem;
    font-family: 'Source Sans 3', Arial, sans-serif;
    font-size: 1.05rem;
    font-weight: 600;
    background: #2E5A45;
    color: white;
    border: none;
    border-radius: 50px;
    cursor: pointer;
    transition: all 0.3s ease;
    letter-spacing: 0.3px;
    margin-top: 0.5rem;
}
.join-submit:hover, .form-submit:hover {
    background: #1F3A2E;
    transform: translateY(-2px);
    box-shadow: 0 8px 20px rgba(46, 90, 69, 0.25);
}
.join-submit:disabled, .form-submit:disabled {
    opacity: 0.6;
    cursor: not-allowed;
    transform: none;
    box-shadow: none;
}
```

---

### 4.7 Join / Form Section

```css
.join-section {
    max-width: 680px;
    margin: 0 auto;
    text-align: center;
    padding: 3.5rem 2.5rem;
    background: rgba(255, 255, 255, 0.7);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(46, 90, 69, 0.15);
    border-radius: 16px;
}

/* Form rows — 2-column grid for name fields */
.form-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1rem;
    margin-bottom: 1rem;
    text-align: left;
}

/* Form fields */
.form-field {
    margin-bottom: 1rem;
    text-align: left;
}
.form-field label {
    display: block;
    font-size: 0.9rem;
    font-weight: 600;
    color: #2C3A4B;
    margin-bottom: 0.4rem;
    letter-spacing: 0.2px;
}
.form-field input,
.form-field select {
    width: 100%;
    padding: 0.85rem 1.15rem;
    font-family: 'Source Sans 3', Arial, sans-serif;
    font-size: 1rem;
    border: 2px solid rgba(46, 90, 69, 0.2);
    border-radius: 8px;
    background: white;
    outline: none;
    transition: all 0.3s ease;
    color: #1B1F23;
}
.form-field input:focus,
.form-field select:focus {
    border-color: #2E5A45;
    box-shadow: 0 0 0 3px rgba(46, 90, 69, 0.1);
}

/* Custom select chevron */
.form-field select {
    appearance: none;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='8' viewBox='0 0 12 8'%3E%3Cpath fill='%232C3A4B' d='M1.41 0L6 4.58 10.59 0 12 1.41l-6 6-6-6z'/%3E%3C/svg%3E");
    background-repeat: no-repeat;
    background-position: right 1rem center;
    padding-right: 2.5rem;
}
```

---

### 4.8 Content Card (about / privacy pages)

```css
.content-card {
    background: rgba(255, 255, 255, 0.65);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(46, 90, 69, 0.12);
    border-radius: 12px;
    padding: 2.5rem;
    margin-bottom: 2rem;
}
```

---

### 4.9 Team Card (about page)

```css
.team-card {
    display: grid;
    grid-template-columns: 1fr 2fr;
    gap: 2.5rem;
    align-items: start;
    background: rgba(255, 255, 255, 0.65);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(46, 90, 69, 0.12);
    border-radius: 12px;
    padding: 2.5rem;
}

.team-photo-img {
    width: 180px;
    height: 180px;
    border-radius: 50%;
    object-fit: cover;
    margin: 0 auto 1rem;
    display: block;
}

.team-name {
    font-size: 1.35rem;
    font-weight: 700;
    color: #1F3A2E;
    margin-bottom: 0.25rem;
}
.team-title {
    font-size: 0.95rem;
    color: #2E5A45;
    font-weight: 600;
    margin-bottom: 1rem;
}

.team-link {
    display: inline-flex;
    align-items: center;
    gap: 0.4rem;
    padding: 0.5rem 1rem;
    background: #E8E6DC;
    border-radius: 50px;
    font-size: 0.85rem;
    font-weight: 600;
    color: #2C3A4B;
    text-decoration: none;
    transition: all 0.3s ease;
}
.team-link:hover {
    background: #2C3A4B;
    color: white;
}

/* Bio list bullets use brass color */
.team-bio li::before {
    content: "\2022";      /* bullet */
    color: #B08B3E;
    font-weight: 700;
}
```

---

### 4.10 Notice Box (privacy page, brass-bordered)

```css
.notice-box {
    background: rgba(255, 255, 255, 0.65);
    backdrop-filter: blur(10px);
    border: 2px solid #B08B3E;
    border-radius: 12px;
    padding: 2rem 2.5rem;
    margin-bottom: 2rem;
}
.notice-box .notice-title {
    font-size: 0.85rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    color: #B08B3E;
    margin-bottom: 0.75rem;
}
```

---

### 4.11 Invite Page Components

**Invite badge:**
```css
.invite-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-size: 12px;
    font-weight: 700;
    letter-spacing: 1.2px;
    text-transform: uppercase;
    color: #B08B3E;
    background: rgba(176, 139, 62, 0.07);
    border: 1px solid rgba(176, 139, 62, 0.18);
    padding: 6px 14px;
    border-radius: 6px;
    margin-bottom: 28px;
}
.invite-badge::before {
    content: '✉';
    font-size: 14px;
}
```

**Founder note card:**
```css
.founder-note {
    display: flex;
    gap: 16px;
    align-items: flex-start;
    margin: 32px 0;
    padding: 24px;
    background: #FFFFFF;
    border: 1px solid #E8E6DC;
    border-radius: 12px;
}
.founder-avatar {
    width: 48px;
    height: 48px;
    min-width: 48px;
    border-radius: 50%;
    background: #2E5A45;
    color: #FAF9F5;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    font-size: 15px;
}
```

**Step numbers:**
```css
.step-number {
    width: 32px;
    height: 32px;
    min-width: 32px;
    border-radius: 50%;
    background: #2E5A45;
    color: #FAF9F5;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 14px;
    font-weight: 700;
}
```

---

### 4.12 Founder Quote (beta page)

```css
.founder-quote {
    margin-top: 2rem;
    padding: 1.5rem;
    background: rgba(46, 90, 69, 0.04);
    border-left: 3px solid #2E5A45;
    border-radius: 0 8px 8px 0;
}
.founder-quote blockquote {
    font-family: 'Crimson Pro', Georgia, serif;
    font-size: 1.1rem;
    font-style: italic;
    color: #1F3A2E;
    line-height: 1.65;
    margin-bottom: 0.75rem;
}
.founder-quote .attribution {
    font-family: 'Source Sans 3', Arial, sans-serif;
    font-size: 0.9rem;
    font-weight: 600;
    color: #6F6D66;
}
```

---

### 4.13 Trust Bar (beta page)

```css
.trust-bar {
    text-align: center;
    padding: 2.5rem;
    background: rgba(255, 255, 255, 0.6);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(46, 90, 69, 0.12);
    border-radius: 16px;
}
.trust-items {
    display: flex;
    justify-content: center;
    gap: 2.5rem;
    flex-wrap: wrap;
}
.trust-item {
    display: flex;
    align-items: center;
    gap: 0.6rem;
    font-size: 0.95rem;
    color: #1B1F23;
    opacity: 0.9;
}
.trust-item .trust-icon {
    font-size: 1.25rem;
}
```

---

### 4.14 Footer

```css
.footer {
    position: relative;
    z-index: 1;
    text-align: center;
    padding: 3rem 5% 2rem;
    color: #6F6D66;
    font-size: 0.9rem;
    opacity: 0;
    animation: fadeIn 1s ease 1.3s forwards;
}
.footer-links {
    margin-bottom: 1rem;
}
.footer-link {
    color: #2C3A4B;
    text-decoration: none;
    margin: 0 1rem;
    transition: color 0.3s ease;
}
.footer-link:hover {
    color: #2E5A45;
}
```

Footer structure: `Home | About | Privacy | Demo | Sign In`
Below links: `Hesvara Caregiver Assistant · Hesvara LLC`
Below that: `© 2026 · We Handle the Busy Work So You Can Get Back to Caring`

---

### 4.15 Status Badge

```css
.status-badge {
    padding: 0.4rem 1rem;
    background: rgba(46, 90, 69, 0.08);
    border: 1px solid rgba(46, 90, 69, 0.2);
    border-radius: 50px;
    font-size: 0.8rem;
    font-weight: 600;
    color: #2E5A45;
    letter-spacing: 0.5px;
}

/* Inline variant (about page) */
.status-badge-inline {
    display: inline-block;
    padding: 0.25rem 0.75rem;
    background: rgba(46, 90, 69, 0.1);
    color: #2E5A45;
    border-radius: 4px;
    font-size: 0.85rem;
    font-weight: 600;
}
```

---

### 4.16 Background Decoration

```css
.background-decoration {
    position: fixed;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    z-index: 0;
    pointer-events: none;
    overflow: hidden;
}
.background-decoration::before {
    content: '';
    position: absolute;
    width: 600px;
    height: 600px;
    background: radial-gradient(circle, rgba(46, 90, 69, 0.04) 0%, transparent 70%);
    top: -200px;
    right: -200px;
    border-radius: 50%;
    animation: float 20s ease-in-out infinite;
}
.background-decoration::after {
    content: '';
    position: absolute;
    width: 400px;
    height: 400px;
    background: radial-gradient(circle, rgba(44, 58, 75, 0.04) 0%, transparent 70%);
    bottom: -100px;
    left: -100px;
    border-radius: 50%;
    animation: float 15s ease-in-out infinite reverse;
}
```

Parallax effect via JS: `decoration.style.transform = translateY(${scrolled * 0.5}px)`

---

## 5. Responsive Breakpoints

### Breakpoint: 900px

| What changes                        | Details                                |
|--------------------------------------|----------------------------------------|
| Problem/solution grid (index)        | `grid-template-columns: 1fr` (stacked) |
| Value grid (beta)                    | `grid-template-columns: 1fr` (stacked) |
| Hero grid (beta)                     | `grid-template-columns: 1fr`, text-align: center |
| Card stack height (beta)             | `260px` (from 320px)                   |
| Team card (about)                    | `grid-template-columns: 1fr`, centered |
| Feature list (about)                 | `grid-template-columns: 1fr`           |
| Stat grid (about)                    | `grid-template-columns: 1fr`           |
| Status grid (about)                  | `grid-template-columns: 1fr`           |

### Breakpoint: 768px

| What changes                         | Details                               |
|---------------------------------------|---------------------------------------|
| Header padding                        | `1.25rem 5%` (from 1.5rem)            |
| Nav                                   | Hidden, becomes vertical dropdown     |
| Mobile menu toggle                    | `display: block`                      |
| Nav (active)                          | `display: flex; flex-direction: column; position: absolute; top: 100%; left: 0; right: 0; background: #FAF9F5; padding: 1.5rem 5%; gap: 1.25rem; border-bottom: 1px solid #E8E6DC; box-shadow: 0 8px 20px rgba(0,0,0,0.08)` |
| H1 (index)                           | `2.25rem` (from clamp)                |
| H1 (about/privacy)                   | `2rem` (from clamp)                   |
| H1 (beta)                            | `2rem` (from clamp)                   |
| Hero buttons (index)                  | `flex-direction: column; align-items: center` |
| Primary/secondary buttons             | `width: 100%; max-width: 280px; text-align: center` |
| Features grid (index)                 | `grid-template-columns: 1fr; gap: 1.25rem` |
| Components grid (beta)                | `grid-template-columns: 1fr; gap: 1.25rem` |
| Join section (index)                  | `padding: 2.5rem 1.5rem`              |
| Form row                              | `grid-template-columns: 1fr` (stacked) |
| Form card (beta)                      | `padding: 1.75rem`                    |
| Content card, team card (about)       | `padding: 1.75rem`                    |
| Content card, notice box (privacy)    | `padding: 1.75rem`                    |
| CTA buttons                           | `flex-direction: column; align-items: center` |
| Trust items (beta)                    | `flex-direction: column; align-items: center; gap: 1rem` |

### Breakpoint: 600px (invite.html only)

| What changes                | Details                                    |
|------------------------------|--------------------------------------------|
| Content padding              | `32px 20px 48px`                           |
| H1                           | `30px` (from 38px)                         |
| Details grid                 | `grid-template-columns: 1fr; gap: 10px`   |
| Detail card                  | `display: flex; align-items: center; gap: 12px; text-align: left; padding: 14px 16px` |
| Detail icon                  | `margin-bottom: 0; font-size: 18px`        |
| Form row                     | `grid-template-columns: 1fr`               |
| Trust line                   | `flex-direction: column; align-items: center; gap: 12px` |
| Nav padding                  | `20px 20px`                                |

---

## 6. Animations & Transitions

### Keyframes

```css
@keyframes fadeInDown {
    from { opacity: 0; transform: translateY(-20px); }
    to   { opacity: 1; transform: translateY(0); }
}

@keyframes fadeInUp {
    from { opacity: 0; transform: translateY(30px); }
    to   { opacity: 1; transform: translateY(0); }
}

@keyframes fadeIn {
    from { opacity: 0; }
    to   { opacity: 1; }
}

@keyframes float {
    0%, 100% { transform: translate(0, 0) scale(1); }
    50%      { transform: translate(30px, -30px) scale(1.1); }
}
```

Invite page uses a simpler `fadeIn`:
```css
@keyframes fadeIn {
    from { opacity: 0; transform: translateY(12px); }
    to   { opacity: 1; transform: translateY(0); }
}
```

### Animation Assignments

| Element                     | Animation                               | Delay  |
|-----------------------------|-----------------------------------------|--------|
| Header                      | `fadeInDown 0.8s ease forwards`         | 0s     |
| Hero                        | `fadeInUp 1s ease forwards`             | 0.3s   |
| Product overview             | `fadeInUp 1s ease forwards`             | 0.5s   |
| Problem/solution             | `fadeInUp 1s ease forwards`             | 0.7s   |
| Benefits                    | `fadeInUp 1s ease forwards`             | 0.9s   |
| Join section                 | `fadeInUp 1s ease forwards`             | 1.1s   |
| Footer                      | `fadeIn 1s ease forwards`               | 1.3s   |
| Sections (about/priv) :nth  | `fadeInUp 1s ease forwards`             | 0.4s–1.15s (staggered by 0.05–0.1s) |
| Background ::before          | `float 20s ease-in-out infinite`        | —      |
| Background ::after           | `float 15s ease-in-out infinite reverse`| —      |
| Invite .content              | `fadeIn 0.6s ease-out`                  | 0s     |

### Hover Transitions

All hover transitions use `transition: all 0.3s ease` unless noted:

- **Buttons**: `transform: translateY(-2px)` + box-shadow
- **Feature cards**: `transition: all 0.4s ease`, `transform: translateY(-4px)` + shadow + border color change + `::before scaleX(1)`
- **Benefit items**: `transform: translateX(4px)` + bg/border color change
- **Nav links**: `color` transition only
- **Footer links**: `color` transition only
- **Stack cards (beta)**: `transition: transform 0.4s ease`
- **Invite submit**: `transition: background 0.2s ease, transform 0.12s ease`, `translateY(-1px)`

---

## 7. Shadows & Borders

### Box Shadows

| Context                          | Value                                      |
|-----------------------------------|--------------------------------------------|
| Primary button hover              | `0 10px 25px rgba(46, 90, 69, 0.25)`     |
| Secondary button hover            | `0 8px 20px rgba(44, 58, 75, 0.2)`       |
| Nav CTA hover                     | `0 6px 16px rgba(46, 90, 69, 0.25)`      |
| Nav sign-in hover                 | `0 6px 16px rgba(44, 58, 75, 0.2)`       |
| Submit button hover               | `0 8px 20px rgba(46, 90, 69, 0.25)`      |
| Feature card hover                | `0 16px 32px rgba(0, 0, 0, 0.08)`        |
| Stack card default                | `0 8px 24px rgba(0, 0, 0, 0.08)`         |
| Mobile nav dropdown               | `0 8px 20px rgba(0, 0, 0, 0.08)`         |
| Form input focus ring             | `0 0 0 3px rgba(46, 90, 69, 0.1)`        |
| Invite form input focus ring      | `0 0 0 3px rgba(46, 90, 69, 0.08)`       |

### Border Radius Scale

| Value   | Usage                                                 |
|---------|-------------------------------------------------------|
| `4px`   | Status badge inline                                   |
| `6px`   | Invite badge                                          |
| `8px`   | Form inputs, benefit items, stat cards, feature items, founder quote (right side), invite form inputs, invite submit, invite step security note |
| `10px`  | Invite detail card                                    |
| `12px`  | Feature cards, content cards, problem/solution cards, team card, notice box, founder note, stack cards |
| `16px`  | Join section, form card, trust bar, CTA section       |
| `50px`  | All pill buttons (primary, secondary, nav CTA, sign-in, status badge, team link, submit) |
| `50%`   | Circular elements (headshot, founder avatar, step numbers) |

### Borders

| Context                | Border                                      |
|------------------------|---------------------------------------------|
| Feature card           | `1px solid rgba(46, 90, 69, 0.1)`          |
| Content card           | `1px solid rgba(46, 90, 69, 0.12)`         |
| Join section           | `1px solid rgba(46, 90, 69, 0.15)`         |
| Status badge           | `1px solid rgba(46, 90, 69, 0.2)`          |
| Form input             | `2px solid rgba(46, 90, 69, 0.2)`          |
| Primary button         | `2px solid var(--evergreen)`                |
| Secondary button       | `2px solid var(--slate-ink)`                |
| Nav sign-in            | `2px solid var(--slate-ink)`                |
| Notice box (privacy)   | `2px solid var(--brass)`                    |
| Section h2 underline   | `2px solid var(--soft-neutral)` (bottom)    |
| Founder quote (beta)   | `3px solid var(--evergreen)` (left)         |
| Feature card accent    | `3px` gradient top line (via ::before)      |
| Mobile nav bottom      | `1px solid var(--soft-neutral)`             |
| Invite page inputs     | `1px solid var(--soft-neutral)`             |
| Invite divider         | `1px solid var(--soft-neutral)` (horizontal)|

---

## 8. Assets

### Images

| File                  | Size  | Usage                                    | CSS Dimensions    |
|-----------------------|-------|------------------------------------------|-------------------|
| `emily-headshot.jpg`  | 686KB | Team section photo (about.html)          | 180x180px, `border-radius: 50%; object-fit: cover` |
| `og-image.png`        | 30KB  | Open Graph / social sharing preview      | 1200x630 (meta)   |
| `favicon.png`         | —     | Referenced in HTML but not present in repo | `<link rel="icon">` |

### Icons — All Emoji-Based (No Icon Library)

| Emoji | Context                                   | Page(s)          |
|-------|-------------------------------------------|------------------|
| 🗼    | Watchtower feature                        | index, about, beta |
| 📋    | CaseFile feature                          | index, about, beta |
| 📝    | Care Log / Daily Record feature           | index, about, beta |
| ⚖️    | CaseMaker feature                         | index, about, beta |
| 🧠    | AI Insights feature                       | index, about     |
| ⏰    | Deadlines benefit                         | index            |
| 📊    | Evidence benefit                          | index            |
| 🔍    | Pattern spotting benefit                  | index            |
| ✍️    | Letter generation benefit                 | index            |
| 📁    | Record keeping benefit                    | index            |
| 💚    | Reduce overwhelm benefit                 | index            |
| ✓     | Success icon (checkmark)                  | index, beta, invite |
| 🔒    | Security / private                        | beta, invite     |
| 🇺🇸    | U.S.-based servers                        | beta, invite     |
| 🚫    | Data never sold                           | beta, invite     |
| 🛡️    | Access control                            | beta             |
| 🗑     | Delete anytime                            | invite           |
| 🔓    | Free access (invite detail)               | invite           |
| 💬    | Your voice (invite detail)                | invite           |
| ✉     | Invite badge (via `::before content`)     | invite           |
| 🌐    | Website link                              | about            |

### SVGs

1. **LinkedIn icon** (about.html, inline SVG):
```html
<svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor">
  <path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/>
</svg>
```

2. **Select dropdown chevron** (data URI in `background-image`):
```
data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='8' viewBox='0 0 12 8'%3E%3Cpath fill='%232C3A4B' d='M1.41 0L6 4.58 10.59 0 12 1.41l-6 6-6-6z'/%3E%3C/svg%3E
```

---

## 9. JavaScript Behaviors

These behaviors need to be preserved in the static rebuild:

1. **Mobile menu toggle** — Click hamburger to toggle `.active` class on both `.mobile-menu-toggle` and `.nav`. Clicking any nav link closes the menu.

2. **Parallax background** — On scroll, translate `.background-decoration` vertically by `scrolled * 0.5` pixels.

3. **Form submission** — Honeypot spam protection (hidden `bot-field` input). On submit: validate email, disable button, show `form-success` state, hide form.

4. **Smooth scroll to `#join`** — CTA buttons link to `#join` anchor for the form section.

---

## 10. Page Structure Summary

### index.html
Header → Hero (centered text + 3 CTAs) → Problem/Solution (2-col) → Features (auto-fit grid, 5 cards) → Benefits (auto-fit grid, 6 items) → Join Beta (form) → Footer

### about.html
Header → Page Header → What We Do (content card) → The Problem (content card + stat grid) → Our Platform (content card + feature list) → Development Status (content card + status grid) → The Team (team card with photo) → CTA Section → Footer

### beta.html
Header → Hero (2-col: text + card stack) → Value Exchange (2-col: get/ask) → Components (auto-fit grid, 4 cards) → Join Form → Trust Bar → Footer

### invite.html
Simple nav (logo only) → Invite Badge → H1 → Intro text → Founder Note → Detail Cards (3-col) → Divider → Form → Success State → Divider → How It Works (4 steps) → Security Note → Trust Line → Footer

### privacy.html
Header → Page Header → Notice Box → 11 Content Sections (each with h2 + content-card) → CTA Section → Footer
