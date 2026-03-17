# RETS 2026 Performance — Master Plan

## The Concept

A 20-minute satirical performance disguised as a presentation. Jon plays "Agent Jon" — a real estate agent who has gleefully automated his entire business with AI, is now completely unhinged about it, and has absolutely no idea where the line is.

Three acts:
- **Act 1 (~8 min)**: The performance — Agent Jon's AI empire, built live on screen
- **Act 2 (~7 min)**: Drop character. Real data. Facts hit harder after the satire.
- **Act 3 (~5 min)**: "So what do we agree to?" — The rules.

The delivery mechanism: a single HTML file (`output/performance/index.html`) that is NOT a slide deck — it's a **performance runtime**. Each keypress/click advances to the next "moment." Some moments are static slides. Some are live interactive demos that run inside the slide. The screen IS the performance.

---

## File Structure

```
output/
  performance/
    index.html          ← the whole thing, self-contained
  website/
    index.html          ← existing presentation (DO NOT TOUCH)
propiq-demo.html        ← existing tool demo (DO NOT TOUCH)
```

---

## Segment Map

### ACT 1 — THE PERFORMANCE

| # | Segment | Type | Key Moment |
|---|---------|------|------------|
| 1 | Opener — "Best Year of My Life" | Static slide | Character established. Stats: 37 properties, $4.2M commissions. |
| 2 | The Secret | Static slide | "I'll let you in on my secret. I have another agent." |
| 3 | AI Listing Copy Demo | Interactive widget | Property details pre-filled → click → AI types listing in real time. "I've never been to this house." |
| 4 | Image Enhancement Demo | Image comparison widget | House with flaws → click removes each one. Escalates to absurdity. |
| 5 | Targeting Ads Demo | Fake Facebook widget | "Signal detected: probate filing, 4 days ago." Ad generates live. The icky moment. |
| 6 | Agency Conversion Arc | Animated org chart | Each of 5 colleagues converts from human → AI, one keypress at a time. |
| 7 | The Firing | Dramatic moment | Cost comparison. "TERMINATE ALL." "I felt bad. For 20 minutes." |
| 8 | Full AI Operation | Montage slide | Social. Market reports. Morning podcast. Valuations. All AI. |
| 9 | AI-to-AI Negotiation | Two-chat widget | Buyer's AI vs Jon's AI. Deal closes. Jon was at the gym. |
| 10 | The Peak | Pause slide | "I am the future of real estate." Long pause. "...Is this okay?" |

### BREAK

| # | Segment | Type |
|---|---------|------|
| 11 | Drop Character | Hard-cut slide — different aesthetic |

### ACT 2 — THE FACTS

| # | Segment | Type |
|---|---------|------|
| 12 | The Numbers Are Real | Stats slide — 82% of US agents, 23% more transactions |
| 13 | Zimbabwe's Position | Stats slide — 91.6% mobile, $119B market, Propertybook |
| 14 | The M-Pesa Frame | Split slide — M-Pesa story → Zimbabwe parallel |
| 15 | Zillow: $500M Disaster | Cautionary tale slide |
| 16 | The Bias Problem | Cautionary tale — $48K undervaluation, whitewashing cases |
| 17 | AI Slop | Cautionary tale — fake listings, hallucinated windows |
| 18 | The Gray Zone | "None of this is illegal. Yet." |

### ACT 3 — THE RULES

| # | Segment | Type |
|---|---------|------|
| 19 | "So what do we agree to?" | Section break / manifesto intro |
| 20 | Rule 1: Disclose | Discussion card |
| 21 | Rule 2: Don't target grief | Discussion card |
| 22 | Rule 3: Know what you're selling | Discussion card |
| 23 | Rule 4: Build the data now | Call to action |
| 24 | Close / QR | Contact + resources |

---

## Segment 4 — Image Enhancement: Planned Beat Sequence

Each keypress removes something, escalating in absurdity:

1. **Beat 1**: Rusty satellite dish on the roofline. Remove. "Standard stuff."
2. **Beat 2**: Abandoned car in the driveway. Remove. "Okay."
3. **Beat 3**: Construction site / scaffolding next door. Remove. "Hmm."
4. **Beat 4**: Neighbor's house blocking the view. Remove. Sky appears. Audience gasps.
5. *Optional Beat 5*: The sky is overcast. Remove clouds. Perfect blue sky. "...I'll stop there."

**Image pairs needed** (generate with Nano Banana):
- House base image (Borrowdale-style, Zimbabwe, nice but modest)
- Same house: + satellite dish added to roof
- Same house: + abandoned car in driveway
- Same house: + scaffolding/construction on adjacent plot
- Same house: + neighboring house blocking view / without (open sky)

**CSS implementation**: Two `<img>` tags per beat, one hidden. Keypress triggers CSS class swap with a smooth transition. The "before" fades out, "after" fades in. Optional: add a subtle "AI processing" spinner that runs 0.8s before the reveal.

---

## Segment 5 — Targeting Ad: Planned Widget

The widget looks like a Facebook ad creation tool. Three data "signals" play out in sequence, each more uncomfortable:

**Signal 1 — Death:**
> Signal detected: Probate filing — Estate of Margaret Ncube
> Property: 4 Khumalo Road, Borrowdale, ~$320,000
> Filed: 4 days ago
>
> [Generating personalized ad...]
>
> "We know this can be a difficult time. When you're ready to think about next steps, we'd love to help. 3-bed home in Borrowdale — $185,000. Fresh start. New chapter."

**Signal 2 — Divorce:**
> Signal detected: Divorce proceedings — Case #ZW-2026-0847
> Joint property: 12 Avondale Crescent, registered both names
> Filed: 11 days ago
>
> [Generating personalized ad...]
>
> "Moving forward? We have 2-bed apartments in Avondale from $95,000. Your space. Your terms."

**Signal 3 — Missed mortgage:**
> Signal detected: 3 consecutive missed bond payments
> Property: 7 Greendale Ave, estimated equity $240,000
> Risk flag: Pre-foreclosure stage 1
>
> [Generating personalized ad...]
>
> "Before the bank gets involved — let us help you sell on your terms. Quick. Dignified. Fair."

Between each: Jon (as character) says "No law against it. In fact... it's great customer service."

---

## Segment 6 — Agency Conversion: Org Chart

Visual org chart with Jon at top and 5 staff nodes:

- **Emily** — Listings Coordinator
- **Marcus** — Social Media
- **Sarah** — Lead Response
- **David** — Market Analysis
- **Priya** — Office Manager

Each keypress: one node transforms. Human icon → robot icon. Gray label → green "✓ Automated" badge. Brief transition animation. A small cost counter updates: "$800/month saved."

After all 5: "Monthly AI tools cost: $47. Monthly savings: $4,000. Math is math."

---

## Zillow Angle — The "Equally Nefarious" Connection

**Note for live delivery (S15 — Zillow cautionary tale):**

Zillow's iBuying scandal had an additional layer beyond "algorithm got the price wrong": Zillow was intentionally suppressing its own Zestimate valuations before buying homes — showing homeowners a lower "estimated value" to reduce their asking expectations, then flipping the property at a higher price. This is the AI-assisted manipulation angle.

Jon's character (Agent Jon) used AI for equally uncomfortable things — life-event targeting, photo manipulation, negotiating without ever speaking to anyone. The Zillow story isn't just a tech cautionary tale; it's a mirror for Agent Jon's gleeful optimisation mindset applied at scale.

**Potential ad-lib for S15:** "Zillow had their own version of Agent Jon. Several thousand of them. Running the same math. What Agent Jon did to individuals — Zillow did to the market."

---

## Segment 7 — The Firing

A stark, minimal slide. Five names with checkboxes, each pre-checked. A button: "SEND TERMINATION EMAILS." Click → progress bar → "5/5 emails sent." Then: "The emails were good. Very empathetic. AI wrote those too."

---

## Segment 9 — AI-to-AI Negotiation Chat

A split-screen chat interface:

Left: **Jon's AI** (PropIQ Agent — teal branding)
Right: **Buyer's AI** (HomeSense AI — blue branding)

Messages appear one at a time, on keypress. A negotiation plays out:

1. PropIQ: "Initial offer: $285,000. Property at 4 Khumalo Rd, Borrowdale."
2. HomeSense: "Comparable sales suggest $265,000. Counter-offer: $268,000."
3. PropIQ: "Seller's bottom line: $275,000. Final offer."
4. HomeSense: "Accepted. Sending digital contract now."
5. PropIQ: "Contract executed. Handover date: April 3."
6. [Both AIs]: "Transaction complete."

Then one final message appears at the bottom, from Jon:
> jon_dallas: great, thx 👍
> *(Sent from iPhone — Jon was at the gym)*

---

## Build Order

1. Write plan.md ← THIS FILE
2. Update brief.md
3. Build HTML shell (all 24 segment placeholders, nav system)
4. Build Segments 1-2 (static slides)
5. Build Segment 3 (AI listing copy widget)
6. Build Segment 4 (image enhancement — CSS placeholder version)
7. Build Segment 5 (targeting ad widget)
8. Build Segment 6 (org chart animation)
9. Build Segment 7 (firing moment)
10. Build Segments 8-10 (operation montage, AI negotiation, peak)
11. Build Segments 11-24 (Act 2 + Act 3)
12. Generate images (Nano Banana) for Segment 4
13. Swap placeholders → real images in Segment 4
14. QA full run-through
15. Polish pass

---

## QA Checklist (run after each build session)

### Navigation
- [ ] Spacebar advances every segment
- [ ] Arrow right advances, arrow left goes back
- [ ] Slide counter updates correctly
- [ ] No dead ends (last slide doesn't crash)
- [ ] First slide shows on load

### Each Interactive Widget
- [ ] AI listing copy: typewriter starts on first advance, completes correctly
- [ ] Image enhancement: all 4 beats work, no flicker
- [ ] Targeting ad: all 3 signals play, ad fades in correctly
- [ ] Org chart: each node converts independently, costs update
- [ ] Firing: email send animation works
- [ ] AI negotiation: messages appear one at a time, final "gym" message lands correctly

### Visual / UX
- [ ] Projector mode: dark bg, white text, readable at 10m
- [ ] No horizontal scroll on any slide
- [ ] Fonts load (Montserrat + Inter from Google CDN)
- [ ] No broken image references
- [ ] Transitions feel right (not too fast, not too slow)
- [ ] Mobile viewable (for post-event sharing)

### Tone / Arc
- [ ] Opener establishes character before any tech is shown
- [ ] Each enhancement beat escalates appropriately
- [ ] Targeting demo has the right pause/discomfort beat
- [ ] Org chart conversion feels gleeful, not dark
- [ ] Firing is funny, not cruel
- [ ] "Is this okay?" lands — there must be silence before it
- [ ] Drop character break is visually and tonally distinct
- [ ] Act 2 stats feel different now (audience has FELT the data)
- [ ] Rules feel like a conversation, not a lecture
- [ ] Close is hopeful, not preachy

---

## Image Generation Notes (Phase 4)

Script: `scripts/generate-images.sh`
Provider: Nano Banana (default)
Output: `images/generated/enhancement/`

Prompts to run:
1. `"Zimbabwe residential house, Borrowdale style, nice modest 3-bedroom, red tile roof, short driveway, daytime, photorealistic, no people"` → base
2. Same + `"large rusty satellite dish bolted to the roof"` → beat-1-before
3. Same + `"abandoned rusted car on the driveway"` → beat-2-before
4. Same + `"construction scaffolding on the adjacent plot to the left"` → beat-3-before
5. Same + `"neighboring large house immediately to the right blocking the view"` → beat-4-before

All "after" images are the base (clean house). Transition between before/after per beat.

---

## Notes on Performance Delivery

- Jon advances manually (click or spacebar) — no timed auto-advance
- The screen IS the character's computer — every demo is "Agent Jon's screen"
- Segments 3-9 should feel like Jon is showing the audience his actual tools
- The "pause" on Segment 10 ("Is this okay?") needs dead air — no auto-advance
- Segment 11 (drop character) should feel like the lights came on
- The rules in Act 3 are discussion prompts, not bullet points — Jon should be able to sit with each one
