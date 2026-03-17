# SimplaDocs Brand Reference Guide

**Status:** Reverse-engineered from live site, Slack conversations, and media assets — March 2026
**Source of truth:** Figma board (managed by Hugo Assunção), GitHub repo `shurtador/simpladocsWebsite`

> ⚠️ This document was assembled from observable brand evidence. It is NOT an official brand guideline — SimplaDocs does not currently have one. Items marked with 🔍 need verification from the Figma board or codebase.

---

## Brand Identity

**Company Name:** SimplaDocs (note capitalization: capital S, capital D)
**Tagline:** Operations Built to Scale
**Founder:** Scott Collier-Weir ("The Coda Guy")
**Positioning:** #1 Coda implementation partner. Boutique consultancy specializing in custom Coda solutions, workflow automation, and operational tooling.
**Founded:** ~2017 (Scott has worked with Coda since early private beta)

---

## Logo

**Primary logo file:** `LogoSimpladocsBlueNoBackground.png`
**Small/app variant:** Created by Hugo (Jan 2026), lives on the Figma board. Optimized for small display contexts like Slack avatars.
**Logo color:** Blue on transparent background
**Storage:** Supabase bucket — `bfwmmlvfkgrprcyaummp.storage.supabase.co/storage/v1/object/public/media/media/`

### Logo Usage Notes
- The logo renders as a wordmark in the primary brand blue
- Hugo created an app-optimized version for small contexts (Slack, favicons)
- The Figma board is the canonical source for all logo variants

---

## Color Palette

### 🔍 Primary Colors (need hex verification from codebase/Figma)

| Role | Description | Estimated Value | Source |
|------|-------------|-----------------|--------|
| **Primary Blue** | Logo color, CTAs, headings | 🔍 Verify in `tailwind.config` or Figma | Logo file, site hero |
| **Dark / Navy** | Hero backgrounds, dark sections | 🔍 Near-black or deep navy | Homepage hero section |
| **White** | Body background, card backgrounds | `#FFFFFF` | Site body |
| **Gray** | Card backgrounds, muted sections, client logo treatment | 🔍 Verify — Scott approved "that gray color is really nice" | Slack #web-redesign, Feb 23 |
| **Warm Accent** | Hugo wanted "some yellow in the mix to warm it up" | 🔍 Not confirmed whether implemented | Slack #web-redesign, Feb 23 |

### Color Application (observed from live site)
- **Hero/banner:** Dark background with light text overlay
- **Section alternation:** White sections alternate with darker/gray sections
- **CTAs ("Let's Talk"):** Likely primary blue or accent
- **Client logos:** Rendered with grayscale + opacity-60 CSS filter (monochrome treatment)
- **Case study cards:** Each has a distinct cover image with brand-colored overlays
- **Stats/numbers:** Large display numbers appear in primary blue or white-on-dark

### How to Extract Exact Values
The fastest path to exact hex values:
1. **Tailwind config:** Check `tailwind.config.js` (or `tailwind.config.ts`) in the GitHub repo (`shurtador/simpladocsWebsite`)
2. **Figma board:** Hugo manages brand colors there — ask him for the exact palette
3. **Browser DevTools:** Inspect any element on simpladocs.com → Computed Styles → look for `color`, `background-color`, `fill`

---

## Typography

### 🔍 Font Families (need verification from codebase)

Based on visual observation of the live site:

| Usage | Likely Font | Notes |
|-------|-------------|-------|
| **Headings** | 🔍 Modern sans-serif (possibly Inter, Plus Jakarta Sans, or similar) | Clean, geometric, medium-to-bold weight |
| **Body text** | 🔍 Same family or complementary sans-serif | Regular weight, good readability |
| **CTAs/buttons** | 🔍 Same as headings | Medium or semibold weight |

### Typography Hierarchy (observed)
- **H1 / Hero headline:** Large, bold — "Operations built to scale."
- **H2 / Section titles:** Medium-large, bold — "Why SimplaDocs?", "How we help"
- **H3 / Card titles:** Medium, semibold — individual service or feature names
- **Body / Descriptions:** Regular weight, comfortable line-height
- **Stats / Numbers:** Extra-large display — "+215", "+15", "+83k"
- **Labels / Tags:** Small, possibly uppercase — "Automation", "Coda Pack", "Budgeting"

### How to Verify
Check the `<link>` tags in the site's `<head>` for Google Fonts imports, or look at the CSS for `font-family` declarations. The repo's `globals.css` or `layout.tsx` will have this.

---

## Voice & Tone

### Brand Voice Characteristics (extracted from website copy and Slack culture)

**Professional but accessible.** SimplaDocs speaks like a trusted advisor, not a corporate vendor. The tone is confident without being arrogant, specific without being jargon-heavy.

**Key voice traits:**
- **Results-first:** Lead with outcomes, not features. "No backfill needed after PM retired" > "We built an automation system"
- **Direct & specific:** Use real numbers. "11x faster workflows, 250+ hours saved" — not "significant improvements"
- **Social proof heavy:** Client quotes and testimonials are central to the brand narrative
- **Warm expertise:** "We spend the time to understand how you work" — not "we leverage our proprietary methodology"
- **Low-ego:** "No black boxes, no technical dependencies, no over-engineered solutions"

### Words & Phrases to Use
- "Operations built to scale"
- "Custom solutions" (not "products" or "software")
- "Eliminate manual work"
- "Replace scattered spreadsheets"
- "Real-time visibility"
- "Custom-built for your specific workflows"
- "From simple workflows to complete operations"
- "Let's Talk" (primary CTA)

### Words & Phrases to Avoid
- Don't call it "software" — it's "solutions" or "systems"
- Avoid generic consulting speak: "synergy", "paradigm", "leverage" (as verb), "optimize" (overused)
- Don't over-promise: "revolutionary", "game-changing" — keep it grounded
- Avoid "we're the best" — let client quotes make that case

### Testimonial Style
Client quotes are displayed prominently with attribution. They emphasize ROI, time savings, and team empowerment:
- Short and punchy quotes are preferred for hero sections
- Longer quotes work in dedicated testimonial sections with full attribution (name, title, company)

---

## Website Architecture

### Tech Stack
- **Framework:** Next.js (migrated from Webflow, Feb 2026)
- **CMS:** Payload CMS (headless, self-hosted on Vercel)
- **Hosting:** Vercel
- **Media storage:** Supabase (bucket: `bfwmmlvfkgrprcyaummp`)
- **Styling:** Likely Tailwind CSS (standard for Next.js projects)
- **GitHub:** `shurtador/simpladocsWebsite`
- **Admin:** `/admin` route on the deployed site

### Site Structure
| Page | URL Path | Notes |
|------|----------|-------|
| Home | `/` | Hero + value props + services + case studies + team + testimonials + FAQ |
| Services | `/services` | Detailed service offerings |
| Work / Case Studies | `/work`, `/work/[slug]` | Client success stories |
| Blog | `/blog`, `/blog/[slug]` | Tutorials, thought leadership (10 posts migrated from Webflow) |
| Team | `/team` | Full team listing |
| Careers | `/careers` | Open positions |
| Contact | `/contact` | Contact form |
| Our Mission | `/our-mission` | Company mission statement |
| Our Process | `/our-process` | How we work |

### Key Visual Components
- **Client logo marquee:** Scrolling banner of client logos (Spotify, Netflix, Qualtrics, MrBeast, etc.). Logos are monochrome with grayscale+opacity treatment. Aim for 8-14 logos for smooth scrolling.
- **Case study cards:** Image cover + client name + title + outcome stat + category tags
- **Team cards:** Profile photo + name + title
- **Stats bar:** Large display numbers with labels
- **Testimonial carousel:** Rotating client quotes with attribution

---

## Design Principles (inferred)

1. **Clean over clever.** Minimal decoration, generous whitespace, clear hierarchy.
2. **Show, don't tell.** Real numbers, real client logos, real testimonials.
3. **Dark/light rhythm.** Sections alternate between dark backgrounds (hero, CTAs) and light backgrounds (content sections).
4. **Card-based information architecture.** Services, case studies, team members, and features all use card layouts.
5. **Mobile-first.** Responsive design expected (standard for Next.js + Tailwind).

---

## Brand Assets Inventory

### Known Asset Locations
| Asset | Location |
|-------|----------|
| Logo variants | Figma board (Hugo manages) |
| Website source code | `github.com/shurtador/simpladocsWebsite` |
| Media files | Supabase storage bucket |
| Client logos | Uploaded via Payload CMS at `/admin` |
| Team photos | Supabase: `profilePicScott`, `profilePicSteven`, `profilePicJordyn`, `profilePicDaniel` |
| Case study covers | Supabase: `NJMDesignsCaseStudyCover.png`, `AlixPartnersCaseStudyCover.png`, etc. |
| Banner images | Supabase: `SimpladocsBannerHomeCompressed.webp` |

### Social Presence
- **Twitter/X:** [@simpladocs](https://x.com/simpladocs) (launched Feb 2026, managed by a dedicated team member)
- **LinkedIn:** [SimplaDocs](https://www.linkedin.com/company/simpladocs)
- **YouTube:** Scott's "The Coda Guy" channel (tutorials, thousands of followers)
- **Coda Gallery:** [SimplaDocs services doc](https://coda.io/@simpladocs/simpladocs-services)
- **Email:** info@simpladocs.com

---

## Action Items to Formalize This Guide

To turn this reverse-engineered reference into a proper brand guide, the team should:

1. **Hugo:** Export the exact color palette from Figma (hex codes for primary blue, dark/navy, gray, any accent colors)
2. **Hugo/Steven:** Confirm the font families from `tailwind.config` or the site's CSS
3. **Hugo:** Create official logo usage guidelines (minimum size, clear space, forbidden treatments)
4. **Scott:** Approve the voice/tone section and add any brand words/phrases that are important to him
5. **Steven:** Document any design tokens or component patterns from the codebase
6. **Team:** Decide if this should live as a Coda doc, a Notion page, or a standalone PDF

---

*Last updated: March 12, 2026*
*Assembled by: Jon Dallas via Claude, from live site analysis + Slack #web-redesign channel + team conversations*
