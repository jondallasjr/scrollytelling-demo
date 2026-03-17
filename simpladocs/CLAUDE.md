# SimplaDocs — Working Context

This folder contains brand assets and web experiences for **SimplaDocs** (simpladocs.com), a Coda implementation consultancy that builds custom operations solutions for growing teams.

---

## The Company

**Tagline:** "Operations built to scale."
**What they do:** Custom Coda solutions that eliminate manual work, replace scattered spreadsheets, and give companies real-time operational visibility — from simple automations to complete operations platforms.
**Stats:** +215 projects, +15 years experience, +83k hours saved, 200+ teams worldwide
**Partner status:** #1 implementation partner for Coda + Superhuman
**Founder:** Scott Collier-Weir ("The Coda Guy") — large YouTube Coda tutorial community

### Services
- Custom Coda Solutions (hiring trackers, budgets, dashboards, CRMs, inventory)
- Workflow Automation (data entry, notifications, cross-tool syncing, approvals)
- Operational Visibility (real-time dashboards, KPIs, spend tracking, team capacity)
- AI Context Engineering
- Coda Packs (integrations: Slack, Google, Jira, Salesforce, HubSpot, Zapier, GitHub)
- Coda Admin as a Service
- Workspace Health Report
- Coda School (self-paced training + 1:1 expert support)
- Doc Review
- Templates

### Notable Clients
Spotify, Netflix, Qualtrics, MrBeast, Fidelity, DoorDash, Baltimore Ravens, Khosla Ventures, AlixPartners, The Shelf, New Mexico Environment Department

---

## Brand Tokens — USE EXACTLY

```css
:root {
  --navy:        #0d2d52;   /* Primary text, dark sections */
  --navy-deep:   #071829;   /* Footer, deepest dark */
  --royal:       #2e57ca;   /* CTAs, links, accents */
  --cyan:        #3de3ff;   /* Gradient end, highlights */
  --sky:         #199bde;   /* Alternative accent */
  --lavender:    #889beb;   /* Secondary accent, category tags */
  --medium:      #2d84ef;   /* Body text on dark backgrounds */
  --ice:         #e4f0fb;   /* Light backgrounds, cards */
  --bg:          #f1f3f6;   /* Page background (Frost) */
  --white:       #ffffff;
  --muted:       rgba(13,45,82,0.55);
  --border:      rgba(13,45,82,0.09);

  /* Signature gradient — CTA buttons ONLY, never body text */
  --grad:        linear-gradient(90deg, #2e57ca, #3de3ff);
  --grad-hover:  linear-gradient(90deg, #003566, #2e7cf7);
}
```

---

## Typography

**Primary:** Rethink Sans — headings, body, UI, nav, CTAs
- Weights: 400 (body), 500 (UI/nav), 600 (H1/H2/buttons), 700 (H3/callouts), 800 (display)

**Accent:** Instrument Serif — **italic only**, never upright
- Use for: hero headlines, section titles, pull quotes, warmth moments
- Never use for body copy

**Google Fonts import:**
```html
<link href="https://fonts.googleapis.com/css2?family=Rethink+Sans:ital,wght@0,400;0,500;0,600;0,700;0,800;1,400&family=Instrument+Serif:ital@1&display=swap" rel="stylesheet">
```

**Type scale:**
- Display: clamp(56px,8vw,96px) · weight 500
- H1: clamp(40px,5vw,64px) · weight 600 · letter-spacing -0.02em
- H2: clamp(28px,4vw,44px) · weight 600
- H3: 20–22px · weight 700
- Body: 16–18px · weight 400 · color: --muted on light, --medium on dark
- Label: 11–12px · weight 700 · uppercase · letter-spacing 0.1em · color: --royal

**Mixed heading pattern (common on site):**
```html
<h2>Custom solutions that <em class="serif-italic">scale</em></h2>
```

---

## Logo

**Primary (CDN, use this):**
```
https://bfwmmlvfkgrprcyaummp.storage.supabase.co/storage/v1/object/public/media/media/LogoSimpladocsBlueNoBackground.png
```
Height: 32px in nav, 56px in hero contexts.

**Local SVG assets** (in `../../documents/distribution/svg/`):
- `logo-prioritary_positive.svg` — horizontal, light backgrounds
- `logo-compact_negative.svg` — compact, dark backgrounds
- `logo-symbol_positive.svg` — S symbol mark, light
- `logo-symbol_negative.svg` — S symbol mark, dark
- `logo-vertical_positive.svg` — stacked, light
- `logo-vertical_negative.svg` — stacked, dark

**Logo rules:**
- Never stretch, skew, or recolor
- Positive (navy) on light; negative (white) on dark/colorful
- Minimum clear space = height of the S symbol on all sides
- No drop shadows, no colors outside brand palette

---

## The Escher Effect (Logo Design Story)

The SimplaDocs logo is inspired by **M.C. Escher's impossible buildings**:
> "Two diagonal shapes are drawn, inspired by Escher's impossible geometry. Those shapes are bridged by a horizontal element. The result is a geometric 'S' that represents impossible connections made real."

**For animations:** The Escher S construction sequence is:
1. Show the construction grid
2. Draw top diagonal (upper-left to lower-right plane)
3. Draw bottom diagonal (different plane — feels "impossible")
4. Add horizontal bridge connecting them
5. The S emerges — dynamic, balanced, impossible made real

Use this narrative whenever the logo or its construction is visualized.

---

## Brand Design Elements

### 1. Construction Grid (background texture)
```css
/* Light version */
background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='80' height='80'%3E%3Crect width='80' height='80' fill='none' stroke='rgba(13,45,82,0.055)' stroke-width='0.5'/%3E%3Cline x1='0' y1='0' x2='80' y2='80' stroke='rgba(13,45,82,0.04)' stroke-width='0.5'/%3E%3Cline x1='80' y1='0' x2='0' y2='80' stroke='rgba(13,45,82,0.04)' stroke-width='0.5'/%3E%3Cline x1='40' y1='0' x2='40' y2='80' stroke='rgba(13,45,82,0.03)' stroke-width='0.5'/%3E%3Cline x1='0' y1='40' x2='80' y2='40' stroke='rgba(13,45,82,0.03)' stroke-width='0.5'/%3E%3C/svg%3E");

/* Dark version */
background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='80' height='80'%3E%3Crect width='80' height='80' fill='none' stroke='rgba(255,255,255,0.05)' stroke-width='0.5'/%3E%3Cline x1='0' y1='0' x2='80' y2='80' stroke='rgba(255,255,255,0.03)' stroke-width='0.5'/%3E%3Cline x1='80' y1='0' x2='0' y2='80' stroke='rgba(255,255,255,0.03)' stroke-width='0.5'/%3E%3C/svg%3E");
```

### 2. Diagonal Section Cuts
```css
clip-path: polygon(0 0, 55% 0, 45% 100%, 0 100%);  /* navy side */
clip-path: polygon(55% 0, 100% 0, 100% 100%, 45% 100%);  /* light side */
```

### 3. Pill Buttons
```css
/* Primary CTA */
padding: 14px 24px 14px 32px; border-radius: 100px;
background: linear-gradient(90deg, #2e57ca, #3de3ff);
color: white; font-weight: 600;

/* With arrow circle */
<button>Let's Talk <span class="arrow-circle">→</span></button>
.arrow-circle { width:40px; height:40px; border-radius:50%; background:rgba(255,255,255,0.2); }
```

### 4. Nav Pills
```css
.nav-pills { background: white; border-radius: 100px; padding: 5px; box-shadow: 0 2px 8px rgba(13,45,82,0.06); }
.nav-pill { padding: 8px 20px; border-radius: 100px; }
.nav-pill.active { background: var(--navy); color: white; }
```

### 5. S Symbol as Decorative Element
The symbol SVG can be used as a large ghost decoration:
```css
opacity: 0.03–0.06; /* very subtle */
position: absolute; pointer-events: none;
```

---

## Files in This Folder

| File | Purpose |
|------|---------|
| `brand.html` | Complete SimplaDocs brand guidelines — colors, typography, elements, voice |
| `simpladocs-official-website.html` | Exported HTML of the live simpladocs.com website |
| `simpladocs-scrollytelling.html` | 30-visualization scrollytelling experience (operations focus) |
| `solutions.html` | Dark-theme scrollytelling — "The Impossible Connection" narrative |
| `SimplaDocs_Brand_Reference.md` | Condensed brand reference |
| `simpladocs-logo.ai` | Adobe Illustrator logo file |

---

## Voice & Tone

**SimplaDocs writes:**
- Confident, not arrogant
- Specific, never vague
- Human warmth alongside technical credibility
- Active verbs: eliminate, connect, automate, build, scale
- Pairs technical nouns with emotional outcomes: "your team's time, back"

**Do say:**
- "Operations built to scale."
- "Eliminate manual work."
- "The impossible connection made real."
- "Built for how your team actually works."

**Don't say:**
- "Leverage synergies"
- "Best-in-class solutions"
- "Digital transformation"
- Anything vague or jargony

---

## Technical Notes for Web Work

### Performance (from project logs)
- Gate ALL canvas animation loops with `IntersectionObserver` — critical when multiple canvases exist
- CSS particles: keep below 15 for smooth performance
- Canvas particles: ~2000 is the sweet spot (gap=4 when sampling from image data)
- `getImageData` only on init, never in animation loop
- `will-change: transform` on parallax/animated elements prevents paint thrash
- Avoid too many `box-shadow` — use `filter: drop-shadow` or canvas instead
- `backdrop-filter` sparingly — GPU memory pressure on mobile

### Animation
- IntersectionObserver threshold: 0.2 is the sweet spot for most reveal animations
- CSS transition: `opacity + translateY` with `transition-delay` for stagger effects
- `max-height: 0 → 600px` with transition for accordion (never `9999px` — slow)
- SVG draw: `stroke-dasharray: length; stroke-dashoffset: length;` → animate to 0
- Counter animation: `setInterval(fn, 20)` with step = target/60

### CSS Scroll-Driven (no JS)
- `animation-timeline: scroll(root block)` — progress bar, zero JS
- `animation-timeline: view()` with `animation-range` — clip-path reveals
- ⚠️ Safari support is patchy — add `@supports` fallback

### Section Rhythm
Alternate section backgrounds for visual cadence:
1. `--bg` (#f1f3f6) with grid texture
2. `--white` for card/content sections
3. `--navy` (#0d2d52) for dark/stats sections
4. `--navy-deep` for footer

### CDN Versions (current March 2026)
- GSAP: 3.13.0 — `https://cdnjs.cloudflare.com/ajax/libs/gsap/3.13.0/gsap.min.js`
- ScrollTrigger: same CDN base + `/ScrollTrigger.min.js`
- Lenis: 1.3.18 — `https://unpkg.com/lenis@1.3.18/dist/lenis.min.js`
- Three.js: r167 — `https://cdn.jsdelivr.net/npm/three@0.167.0/build/three.module.js`
- **Lenis + GSAP:** always add `gsap.ticker.lagSmoothing(0)`

---

## Common Patterns

### Scroll-triggered reveal
```js
const observer = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.classList.add('visible');
      observer.unobserve(e.target); // fire once
    }
  });
}, { threshold: 0.2 });
document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
```

### Animated counter
```js
function animateCounter(el, target, duration = 2000) {
  const start = performance.now();
  function update(now) {
    const progress = Math.min((now - start) / duration, 1);
    const eased = 1 - Math.pow(1 - progress, 3); // ease-out cubic
    el.textContent = Math.floor(eased * target).toLocaleString();
    if (progress < 1) requestAnimationFrame(update);
  }
  requestAnimationFrame(update);
}
```

### Canvas boilerplate with IntersectionObserver gate
```js
let animating = false;
let rafId;

function draw() {
  if (!animating) return;
  // ... drawing code ...
  rafId = requestAnimationFrame(draw);
}

const observer = new IntersectionObserver(([entry]) => {
  animating = entry.isIntersecting;
  if (animating) draw();
  else cancelAnimationFrame(rafId);
}, { threshold: 0.1 });

observer.observe(canvas);
```
