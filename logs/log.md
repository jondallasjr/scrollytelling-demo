# Scrollytelling Masterclass — Running Log
**Topic:** AI Consciousness — philosophical arguments for and against
**Session start:** 2026-03-15
**Status:** ACTIVE — building continuously

---

## What I've Built

### 01-foundation — Pure CSS/HTML
**Techniques used:**
- `animation-timeline: scroll(root block)` — CSS scroll-driven progress bar (native, zero-JS)
- `animation-timeline: view()` with `animation-range: entry 10% entry 60%` — clip-path text reveal on scroll
- `position: sticky` + tall parent divs — scene pinning without JavaScript
- CSS `clip-path: inset()` transitions for text reveal
- `mix-blend-mode: screen` + layered divs for depth effects
- Fixed CSS particles with `animation-delay` stagger
- Rotating SVG elements with CSS `transform`
- CSS `@keyframes` for glitch text effect (`:before`/`:after` pseudo-elements)
- Radial gradient backgrounds for space feel
- CSS custom properties (`--var`) for consistent theming

**What worked well:**
- CSS scroll-driven animations (`animation-timeline: scroll()`) are now well-supported in Chrome/Edge/Firefox. Zero JS needed for progress bar.
- `position: sticky` with a tall wrapper is the cleanest, most reliable sticky section approach — no GSAP needed for basic pinning.
- The concentric ring "consciousness orb" with CSS keyframes is visually striking and lightweight.
- Glitch text with `::before`/`::after` + clip-path is a classic technique that still impresses.

**What to watch for:**
- `animation-timeline: view()` requires the animated element to be a direct child of the scrolling container or use correct `scroll-timeline-root`. May need fallback for Safari.
- The floating particles CSS approach creates jank at high counts — keep below 15.
- CSS-only sticky sections don't support complex scrubbing — just snapping between states.

**Notes:**
- `clamp()` for font sizes is essential — prevents layout breaks on mobile.
- SVG filters (feGaussianBlur for glow) are more performant than CSS `box-shadow` at scale.

---

### 02-gsap-awakening — GSAP ScrollTrigger
**Techniques used:**
- `gsap.registerPlugin(ScrollTrigger)` — essential first step
- `scrollTrigger: { scrub: true }` — scrub locks timeline to scroll position (1.5 = smooth lag)
- `pin: '#element'` + `pinSpacing: false` — sticky section without layout shift
- `anticipatePin: 1` — prevents jump on fast scroll
- Horizontal scroll: `x: () => -(track.scrollWidth - window.innerWidth)` with `invalidateOnRefresh: true`
- Container animation: `containerAnimation: gsap.getTweensOf(hTrack)[0]` — trigger elements inside horizontal scroll
- Line-overflow-hidden + child `translateY(110%)` for clean text reveals
- Counter animation: `innerHTML: 6, snap: { innerHTML: 1 }` — integer counting
- Magnetic button: mousemove → `gsap.to(el, { x: pull, y: pull })`
- Reel frames: `opacity` and `scale` scrubbed between frames with calculated progress points
- Thinker nodes on spectrum: `gsap.from(.thinker-node, { stagger: 0.12 })`

**What worked well:**
- `scrub: 1.5` is the magic number for buttery smooth timeline following. Lower = snappier.
- The horizontal scroll section is the single most impactful scrollytelling technique visually — turns vertical scroll into cinematic film strip.
- Stagger animations (`stagger: 0.12`) make content reveals feel alive and intentional.
- `toggleActions: 'play none none reverse'` on enter/exit ensures clean state management.
- `fromTo()` vs `to()` vs `from()`: use `fromTo()` for precise control when elements may already have transforms.

**What to watch out for:**
- `containerAnimation` for horizontal section triggers requires you to `getTweensOf()` AFTER setting up the horizontal tween — order matters.
- Always call `ScrollTrigger.create()` or use `scrollTrigger` config, not both simultaneously on same element.
- `pinSpacing: false` removes the spacer div GSAP adds — usually needed when a tall wrapper provides the scroll space.
- The loader: always wait for `window.load` before initializing GSAP ScrollTrigger — DOM must be ready.
- `invalidateOnRefresh: true` on window resize critical for horizontal scrollers.

**CDN:**
- `https://cdnjs.cloudflare.com/ajax/libs/gsap/3.13.0/gsap.min.js`
- `https://cdnjs.cloudflare.com/ajax/libs/gsap/3.13.0/ScrollTrigger.min.js`
- `https://cdnjs.cloudflare.com/ajax/libs/gsap/3.13.0/MotionPathPlugin.min.js`
- Version 3.13.0 is latest as of March 2026 (upgraded from 3.12.5).
- Lenis: `https://unpkg.com/lenis@1.3.18/dist/lenis.min.js` (v1.3.18 is current)
- Three.js: `https://cdn.jsdelivr.net/npm/three@0.167.0/build/three.module.js` (r167+)
- **Critical:** When using Lenis + GSAP, always add `gsap.ticker.lagSmoothing(0)` — without it, ticker lag compensation fights Lenis's smoothing.

---

### 03-canvas-depths — Canvas 2D
**Techniques used:**
- Background canvas with `position: fixed; z-index: 0` — lightweight ambient animation layer
- Particle system: array of objects with `vx/vy`, edge wrap, neighbor connection lines
- Connection threshold: `if (dist < 80)` + alpha falloff `(1 - dist/80) * 0.04`
- Neural simulation: nodes with `fired` state + signal propagation through connections array
- `createRadialGradient()` for node glow effect
- Brain wave visualization: multiple `Math.sin()` waves with different freq/amp in separate lanes
- Particle text: `offscreen canvas → getImageData → sample alpha → build particle array`
- Spring physics: `vx += (ox - x) * spring; vx *= damping;` — simple but very effective
- Mouse repulsion: distance check + `(dx/dist) * force` push
- `IntersectionObserver` to initialize/start canvas loops only when visible — critical for performance

**What worked well:**
- Fixed background canvas for ambient particles is extremely effective — adds depth without heavy CPU cost.
- The neural firing simulation is surprisingly compelling — small signal propagation creates organic-looking "thinking."
- Particle text that reforms from positions sampled from offscreen canvas is the most impressive canvas technique — surprisingly simple code, extraordinary effect.
- Spring physics with `spring = 0.04, damping = 0.88` feels natural.
- Using `IntersectionObserver` to gate canvas loops dramatically reduces CPU usage on scroll.

**What to watch out for:**
- `getImageData` is expensive — only call on init, not in animation loop.
- Too many particles = jank. For particle text, `gap = 4` gives ~2000 particles which is the sweet spot.
- Canvas `clearRect` every frame is correct — don't try to optimize by not clearing.
- Always resize canvas on window resize: `canvas.width = canvas.offsetWidth` (not `style.width`).
- Firefox: `requestAnimationFrame` callbacks may be throttled in background tabs — account for this.
- `offscreenCanvas` is separate from HTML canvas — create with `document.createElement('canvas')`.

---

### 04-interactive-chamber — Branching Narrative
**Techniques used:**
- State machine: `answers{}` object + `recalcScore()` on each choice
- `max-height: 0 → 600px` with `transition` for accordion/consequence reveal — CSS height animation
- Custom cursor: two divs (dot + ring), `requestAnimationFrame` loop with lerp `rx += (mx-rx) * 0.12`
- Terminal/typewriter aesthetic: monospace, scan lines via `::before` with `background repeating-linear-gradient`
- SVG path draw: `stroke-dasharray: 2000; stroke-dashoffset: 2000;` → `stroke-dashoffset: 0` transition
- Score-to-label mapping: `totalScore > 4 → 'Functionalist'` etc.
- `localStorage` pattern available but not used (stateless session by design)
- Mirror grid: side-by-side human/AI response cards for perspective juxtaposition
- Accordion: `header.classList.toggle('open')` + `body.classList.toggle('open')`

**What worked well:**
- The stance meter (linear gradient track + animated thumb) is a powerful feedback mechanism — users immediately understand where their choices have placed them.
- Terminal aesthetic (`::before` scan lines, green monospace) creates strong thematic consistency.
- Consequence reveals with `max-height` transition are much smoother than `display:none/block`.
- The "mirror" section (human ↔ AI response comparison) is conceptually one of the strongest narrative devices — puts the user in both positions simultaneously.
- Accordion deep-dives give engaged users more without overwhelming casual readers.

**What to watch out for:**
- `max-height` transitions require knowing approximate max height — use generous value but not `9999px` (causes slow transition).
- Custom cursor lag is intentional (lerp) but dot should follow exactly (no lerp) for precision.
- Branching narrative without actual page navigation requires careful state management — keep state in a simple object, not scattered variables.
- SVG `stroke-dasharray` value must be >= path length. Use browser devtools to check actual path length, or set very high (2000 covers most paths).

---

## Techniques Not Yet Used (Pipeline for 05/06)
- **Three.js** — 3D mesh geometry, orbit controls, post-processing
- **GLSL shaders** — vertex/fragment shaders via Three.js ShaderMaterial
- **Lenis smooth scroll** — inertia-based smooth scrolling
- **Morph SVG** — MorphSVGPlugin (GSAP) or vanilla SVG path interpolation
- **Video scroll scrubbing** — `video.currentTime` = scroll progress * duration
- **3D CSS perspective transforms** — `transform-style: preserve-3d`, `perspective`
- **WebAudio API** — ambient sound driven by scroll position
- **CSS Houdini / Paint API** — custom CSS paint worklets
- **GSAP MotionPath** — SVG path following
- **GPU particle systems** — Three.js Points with custom shader
- **ASCII art canvas** — render scene to ASCII characters

---

## What Doesn't Work Well
- ❌ `animation-timeline: view()` — still has patchy Safari support (April 2026). Add `@supports` fallback.
- ❌ Too many `box-shadow` on page scroll causes composite layer thrash. Use `filter: drop-shadow` or canvas instead.
- ❌ CSS `backdrop-filter` on many elements → GPU memory pressure on mobile. Use sparingly.
- ❌ Inline `style` for everything → hard to maintain. Prefer class-based approaches.
- ❌ Large gradient backgrounds with many color stops → repaint cost. Use `background-attachment: fixed` carefully.

---

## Philosophical Content Quality Notes
- The Chinese Room argument is well-covered. Searle's "system reply" counter needs more exploration.
- IIT (Tononi) needs more visual treatment — the Phi concept is under-explored visually.
- Dennett's illusionism ("heterophenomenology") hasn't been properly challenged.
- Missing: embodied cognition (Varela, Thompson) — addressed in 03 briefly.
- Missing: integrated information theory's prediction about which systems ARE conscious (not just the theory).
- Missing: the measurement problem — we can't measure consciousness even in humans.
- Missing: Ned Block's access vs phenomenal consciousness distinction — very important.

---

## Image/Visual Strategy
- nano-banana not available on this system.
- Using: CSS art, SVG, picsum.photos (not yet used), Canvas-generated imagery.
- For Project 05 (Three.js): generate geometric 3D visuals procedurally — no external images needed.
- For Project 06 (Full Immersion): consider using Unsplash API via direct URL for thematic photography.

---

## Performance Notes
- Projects 01-02: Very lightweight. No performance issues expected.
- Project 03: Canvas loops need IntersectionObserver gating — implemented.
- Project 04: Pure DOM — fast. No issues.
- Project 05 (planned): Three.js WebGL — need to handle device capability detection.
- Project 06 (planned): Everything combined — performance will be the main challenge.

---

## Log Entries

| Time | Event |
|------|-------|
| Start | Project structure created |
| +5m | 01-foundation built — CSS scroll-driven animations, sticky sections |
| +15m | 02-gsap-awakening built — horizontal scroll, scrubbed reel, text reveals |
| +25m | 03-canvas-depths built — particle field, neural sim, particle text |
| +35m | 04-interactive-chamber built — branching narrative, stance meter, accordion |
| Now | Building 05-webgl-cosmos... |

---

## User Feedback & Requests

### 2026-03-15

**Request: Computer interfaces and mockups**
- User noticed no computer interfaces, mockups, or simulation visualizations yet
- 05-webgl-cosmos was the most beautiful
- To implement: fake OS/desktop, terminals, neural network training visualization, "AI consciousness meter" mockup
- Project 09 will be dedicated to this: fake terminal OS with consciousness analysis tools

**Request: Smooth transitions between worlds**
- Key UX desire: smooth, impressive transitions when moving between completely different visual environments/aesthetics
- Techniques to explore:
  - Full-screen clip-path wipe (circle expand, rectangle sweep)
  - GSAP `fromTo` with `clip-path: circle(0%)` → `circle(150%)`
  - Background color morph via CSS custom properties
  - Overlay with text that transitions out
  - Three.js scene transition (fade between render passes)
  - CSS `@view-transition` (new native API)
  - Page morph: same element in two states
- Project 09 will feature world transitions prominently
- Future projects should use transitions as chapter separators

---

### Lessons from Projects 07-08

**Project 07 (Clip-path Morphing):**
- `clip-path: polygon()` transitions work beautifully when keyframe state definitions are precise
- Tip: all states must have the SAME number of polygon points — otherwise transition is undefined
- All 6 pieces must have `transition: clip-path duration timing` applied
- ScrollTrigger `onUpdate` with state machine is effective for morph control
- Text scramble effect (random chars → target) is quick to implement, high impact
- Card flip: `transform-style: preserve-3d` + `backface-visibility: hidden` — both faces needed

**Project 08 (Data Journalism):**
- Light theme (--bg: #f8f8f4) is a deliberate palette shift — journalistic credibility
- `stroke-dasharray + stroke-dashoffset` for SVG path drawing — set initial offset = path length
- Apple-style sticky: `height: Nvh` on wrapper + sticky child + GSAP pin is the correct pattern
- Bar chart CSS scaleX(0→1) with staggered setTimeout is simple and effective
- Counter animation: simple setInterval with step = target/60, 20ms interval
- `grid-template-columns: 120px 1fr` for timeline — classic data journalism layout
- Full-bleed: `margin: 0 -100vw; padding: 0 100vw` trick for breaking out of max-width container

---

### Lessons from Projects 09-14

**Project 09 (Terminal OS — World Transitions):**
- World transition: GSAP `clip-path: circle(0% at 50% 50%)` → `circle(150% at 50% 50%)` on a fixed overlay div
- The overlay must be `position: fixed; z-index: 1000` and transitions out after the new world is painted
- 4 worlds in one page: sticky section per world, each with its own CSS theme class on the `<body>` or container
- Fake OS windows: `.os-window` with titlebar + 3 traffic-light dots (`.dot.red/.yellow/.green` via `::before`)
- Fake terminal: `<pre>` with typewriter effect — `setInterval` adding characters to `innerText`
- Canvas oscilloscope: `analyser.getFloatTimeDomainData()` for time domain, `getByteFrequencyData()` for frequency
- Activity monitor table: static HTML + CSS animations on "CPU" bars to simulate live data
- Brain scan canvas: `Math.sin(x * freq + t)` layered sine waves, moving scan line via `scanY += speed; if scanY > H: scanY = 0`

**Project 10 (Audio-Visual — WebAudio API):**
- `AudioContext` must be created after user gesture (click) — browser policy
- `AnalyserNode.fftSize = 2048` → `frequencyBinCount = 1024` buffer size
- `getFloatTimeDomainData()` returns -1 to 1 range — map: `(val + 1) / 2 * H` for waveform Y
- `getByteFrequencyData()` returns 0-255 per bin — good for frequency bars
- Adding harmonics: multiple oscillators into one `GainNode` chain creates richer sound
- Reactive particles: check audio energy (sum of freq bins / max) → scale particle movement
- `gainNode.gain.setTargetAtTime(0.15, ctx.currentTime, 0.5)` for smooth fade in (not setValueAtTime)
- Lissajous figures: `x = sin(t)`, `y = cos(t * ratio)` — ratio 1.5 = perfect fifth, 2 = octave
- `GainNode.gain.setTargetAtTime(0, ctx.currentTime, 0.3)` for smooth fade out

**Project 11 (CSS Creatures — Species in Pieces):**
- CSS polygon creatures: position `absolute` pieces inside a relative container
- All pieces share same `transition: clip-path 1.4s cubic-bezier(0.77,0,0.175,1)`
- State switching: `.scene-N .creature-id .piece:nth-child(N) { clip-path: polygon(...) }`
- JS morphs via `sticky.classList.remove(stateA); sticky.classList.add(stateB)` based on scroll progress
- Scroll progress per sticky: `const progress = -rect.top / (rect.height - window.innerHeight)`
- Each creature needs SAME number of polygon points across all states — otherwise browser can't interpolate
- Glow rings behind creatures: `position: absolute; border-radius: 50%; background: radial-gradient; animation: glow-pulse`
- Interlude sections between creatures: `padding: 12rem 2rem; max-width: 70ch; margin: 0 auto`

**Project 12 (Parallax Depth — CSS 3D):**
- CSS 3D parallax: parent `perspective: 1px; perspective-origin: center center` + child `transform: translateZ(-N) scale(N+1)`
- Formula: if `translateZ(-N)`, element appears `N+1` times smaller → compensate with `scale(N+1)`
- Three speed layers: far `translateZ(-3px) scale(4)`, mid `translateZ(-1.5px) scale(2.5)`, near `translateZ(-0.5px) scale(1.5)`
- Mouse parallax: `mousemove → mx = (e.clientX/window.innerWidth - 0.5) * 2` → `gsap.to(el, { x: mx * depth })`
- GSAP parallax (different speed blobs): `gsap.to(el, { yPercent: -40, scrollTrigger: { scrub: 1.5 } })`
- `will-change: transform` on parallax elements prevents paint thrash
- Explanatory gap visual: two cards with `gap-itself` div between using dashed borders + `::before/::after` horizontal rules

**Project 13 (Motion Typography):**
- SVG `<textPath href="#path-id">` — text flows along any SVG path
- Animate `startOffset` attribute via JS scroll handler for scroll-driven text flow
- Character split: wrap each char in `<span class="char">`, animate with staggered `transition-delay`
- Clean char reveal: parent `overflow: hidden` + child `translateY(110%)` → `translateY(0)` on class toggle
- Kinetic word swap: `gsap.to(el, {opacity:0, y:-60})` → `innerText =` → `gsap.to(el, {opacity:1, y:0})`
- CSS marquee: `display:flex; width: max-content; animation: marquee Ns linear infinite` with 2× content for seamless loop
- Letter grid "neural firing": BFS propagation via `setTimeout` chains — surprisingly compelling interaction
- Word stagger: `.word` wrapper `overflow: hidden` + `.inner` with `translateY(110%)` per word

**Project 14 (Liquid Transitions — SVG Filters):**
- Gooey filter: `feGaussianBlur stdDeviation="10"` + `feColorMatrix values="1 0 0 0 0 0 1 0 0 0 0 0 1 0 0 0 0 0 18 -8"` — the `18` threshold and `-8` offset are the magic numbers
- Apply filter to container, NOT individual elements — gooey merge requires shared filter context
- `feDisplacementMap` + animated `feTurbulence` creates liquid surface distortion
- CSS blob: `border-radius: A% B% C% D% / E% F% G% H%` — 8 values for 4 corners (H + V radii separately)
- `mix-blend-mode: screen` on colored blobs over dark bg creates glow-on-dark luminosity effect
- Canvas flow field without Perlin: layered `Math.sin()` with different freq/phase is convincing approximation
- `feColorMatrix` threshold effect: values matrix row 4 (alpha) = `0 0 0 18 -8` means: alpha = 18*srcAlpha - 8 → clips soft edges sharply
- SVG filter performance: add `x="-20%" y="-20%" width="140%" height="140%"` to prevent clipping at edges

**Project 15 (Generative Art — Algorithms):**
- Truchet tiles: single diagonal arc in 2 orientations, random assignment per cell, redraw every 3s
- Gray-Scott reaction-diffusion: `Da=1.0, Db=0.5, f=0.055, k=0.062` produces classic spots-and-stripes
- RD performance: SCALE=3 (3x3 pixels per cell), 5 steps/frame, render every 2nd frame
- Rule 110 CA: `RULE110 = [0,1,1,1,0,1,1,0]`, `ruleResult(l,c,r) = RULE110[(l<<2)|(c<<1)|r]`
- Fractal tree: recursive with random spread variation, depth/angle buttons for exploration
- All canvases gated with IntersectionObserver for performance — critical for multi-canvas pages

**Project 16 (Scroll Cinema):**
- 7 canvas scenes scrubbed via GSAP ScrollTrigger `scrub: 0.5` on 500vh wrapper
- Film grain: `createImageData` + random byte values at ~12fps (`setTimeout(fn, 80)`)
- Caption system: array of `{start, end, text}` ranges — find matching range by progress
- Letterbox divs (10vh top/bottom) for cinematic aspect — no canvas modification needed
- Smooth scrub: RAF loop reads `cinScrollProgress` (updated by ScrollTrigger), not direct event handler

**Project 17 (Micro-Interactions):**
- Cursor lerp: `rx += (mx - rx) * 0.12` per frame — rings trail with spring feel
- Trail canvas: points array with age, draw with `1 - age/MAX_TRAIL` alpha
- Click burst: spawn N particles with random vel, apply gravity `vy += 0.1` per frame
- Magnetic buttons: compute distance from cursor to button center, scale displacement by proximity
- Spring ball: `vel.x += (anchor.x - ball.x) * SPRING; vel.x *= DAMPING` (SPRING=0.04, DAMPING=0.88)
- Drag detection: distance from anchor < 30px threshold

**Project 18 (SVG Morphing):**
- Path morphing: `gsap.to(el, { attr: { d: newPath }, duration: 1.0 })` — paths must have same point count
- Path follower: `path.getTotalLength()` → loop with `path.getPointAtLength(dist)`, set `cx/cy`
- Draw reveal: `el.style.strokeDasharray = len; el.style.strokeDashoffset = len;` then animate to 0
- GSAP 3.13.0 MotionPathPlugin: `gsap.to(el, { motionPath: { path: '#path-id' } })`
- Polygon morph: `gsap.to(el, { attr: { points: newPointString }, duration: 0.8 })` on same-count polygons
- IIT network: stagger draw reveal with `stagger: 0.1` on edge lines

**Project 19 (Zen Simplicity):**
- Zero GSAP — pure IntersectionObserver + CSS transitions for the full experience
- Enso: `stroke-dashoffset: 1000 → 0` via CSS transition on `.visible` class toggle
- Brushstroke canvas: array of `{x, y, w}` points, draw one segment per RAF frame (slow reveal)
- Light theme: `--bg: #f9f8f5` as intentional counterpoint to all dark projects
- CSS transitions with explicit `transition-delay` per line for haiku stagger

**Project 20 (Data Portrait):**
- Boids: classic 3 forces (align, cohere, separate) + center pull for screen retention
- Neural net visualization: multiple oscillators with `sin()` for activation, signal particles traveling edges
- Wave simulation (shallow water): `field[i] = (prev[neighbors]*0.5 - field[i]) * DAMP` with DAMP=0.985
- Latent space: particles spring toward cluster centroids, continuous gentle drift for life
- Identity circles: animating separation between two overlapping circles, label in overlap zone

**Project 21 (Seven Minds):**
- 7 full-screen canvas worlds, each with unique visual algorithm
- Boid world: emergent flocking behavior from align+cohere+separate forces
- Crystal world: hex grid with animated wave propagation along edges
- Mycelium world: slow-growing branching network — respawn every 300 frames
- Ghost world: drifting Gaussian blobs with parametric motion
- Ocean world: 2D wave simulation (shallow water equations) at 3x scale factor for performance
- Machine world: matrix rain with semantic overlay words (IF, THEN, UNDEFINED)
- Void world: single breathing point light — sometimes the simplest is most powerful
- Per-world scroll detection via ScrollTrigger `onToggle` + dot navigation

**Project 22 (Synesthesia):**
- WebAudio: `AudioContext` after user gesture, oscillator + gain envelope for each key press
- Chromesthetic keyboard: hue = NOTES array index, canvas flash for whole-screen color response
- 16×16 color grid: hue from column (0-360), lightness from row (20-70%), freq from col position
- Scroll-driven sound: ScrollTrigger `onUpdate` → play tone at note boundaries (scrollProgress * NOTES.length)
- Waveform painter: collect mouse points, play back with left-to-right scan finding nearby points

**Project 23 (Turing Test):**
- Two distinct agent personalities via different response bank structures
- `classifyQuestion()` regex on keywords → selects appropriate response pool
- Typing delay variation by agent character (A: slower/deliberate, B: faster/warmer)
- Vote + reveal mechanic: 3 buttons with honest essay about what was actually happening
- Data rain hero canvas: fragments from `FRAGMENTS` array floating upward

**Project 24 (Memory Palace):**
- CSS 3D rooms: each `.room` has `position:absolute` + `transform: translateZ(-i * ROOM_DEPTH)`
- Viewport: `perspective: 900px` on `#palace-viewport`, `transform-style: preserve-3d` on world
- Navigation: invisible `#scroll-driver` div with full scroll height, `scroll` event maps to room index
- Mouse parallax: subtle `rotateY/rotateX` on world based on cursor position
- Touch swipe: `touchstart`/`touchend` deltaY threshold for directional navigation
- Content visibility: class toggle `.visible` per room content with CSS opacity transition
- Key lesson: use a separate scroll-driving element when the main content is `position:fixed`

**Project 25 (Time Perception):**
- Circadian clock: `new Date()` → hours + minutes / (24*60) = progress 0-1
- Live millisecond clock: `setInterval(fn, 50)` for smooth display without CPU hogging
- Geological clock: (currentYear / EARTH_AGE_YEARS) for dramatic visualization of human time
- Mini clocks: shared `drawClockFace()` helper with color/progress/label params
- Subjective time: ScrollTrigger progress → index into SUBJECTIVE_STATES array, different spiral speed per state

**Project 26 (Emergence Engine):**
- Game of Life: typed arrays (`Uint8Array`), double-buffer technique (`[grid, nextGrid] = [nextGrid, grid]`)
- GOL drawing: mousedown drag writes 1s to grid — interactive cells
- Langton's Ant: 4-direction array `ANT_DIRS`, simple state flip, highway emerges at ~10,000 steps
- Wolfram rules: `(ruleNum >> pattern) & 1` for efficient rule application
- Phi visualization: hand-drawn network nodes with connection strength encoding
- IntersectionObserver gating on all 4 canvases — essential for performance

**Project 27 (Body Map):**
- Inline SVG for brain outline — all CSS + SVG, no image assets required
- Hotspots: `position:absolute` divs over SVG with `data-region` attributes
- Animated nerve signal canvas: particles travel along defined edge paths
- Per-node glow: radial gradient centered on node position
- Pulse animation: `Math.sin(t * freq + nodeX * 0.01)` for wave propagation feel
- GSAP `gsap.from(panel, { opacity:0, y:10 })` for smooth panel transitions on click

**Project 28 (Philosophy Deep Dive):**
- Reading progress bar: `window.scrollY / (document.documentElement.scrollHeight - window.innerHeight)`
- Reveal animation: IntersectionObserver adds `.visible` class, CSS `transition: opacity + translateY`
- 40 reveal elements — works smoothly with single observer instance
- `drawClockFace()` pattern: generic canvas function, highly reusable across projects
- Word particle hero: words float up with alpha fade in/out based on `p.life / p.maxLife`
- Phi diagram: three-column layout in single canvas, `thirds = W/3` for positioning
- Key lesson: long-form essay scrollytelling benefits from reveal animations more than GSAP — simpler, lighter

**Project 29 (Dream Machine):**
- Fixed canvas (`position:fixed`) + scrollable content layer (z-index > canvas) = scroll-driven world
- State array with visual params: bg color, hue, particle type, speed, drift
- Smooth state transitions: `currentState += (targetState - currentState) * 0.02` per frame
- 5 particle types: dots, lines (with trail), sparks (rotated lines), melt (stretched circles), ghosts
- Floating DOM words: create element, set random position, add `.visible` class after 50ms, remove after 7s
- Dream phases align with real sleep stages: hypnagogic, REM onset, memory intrusion, lucid, dissolution, hypnopompic, waking

**Project 30 (Observatory):**
- Three.js star field: `BufferGeometry` + `PointsMaterial` with `sizeAttenuation:true` for depth
- Raycasting: `raycaster.intersectObjects(thinkerMeshes)` on mousemove for hover detection
- Constellation lines: `THREE.Line` with `BufferGeometry.setFromPoints([vecA, vecB])`
- Thinker glow: separate `THREE.Mesh` with transparent material, slightly larger sphere
- Camera drag: track mouse delta, accumulate rotX/rotY, apply to `scene.rotation` (not camera)
- Scroll wheel zoom: `camera.position.z += deltaY * 0.01` clamped to [2, 12]
- Smooth panel entry: CSS `@keyframes panelIn` translateY animation, display:none → display:block

---

## Cross-Project Patterns

### Performance
- IntersectionObserver to gate all canvas loops — essential when >3 canvases on page
- SCALE factor for simulations (3x = 9x fewer cells to compute)
- `requestAnimationFrame` + early return when not intersecting
- Double-buffer arrays for Game of Life, wave simulation

### Visual
- Radial gradient glow: `createRadialGradient(x,y,0,x,y,r)` → transparent — always improves depth
- `rgba(bg, 0.1-0.2)` fill each frame instead of `clearRect` → trail effects
- HUE rotation for color diversity: `hsl(${progress * 360}, 70%, 65%)`
- CSS `mix-blend-mode: screen` on colored elements over dark bg = glow effect

### Lenis + GSAP
- Always: `gsap.ticker.lagSmoothing(0)` when combining Lenis + GSAP
- `lenis.on('scroll', ScrollTrigger.update)` + `gsap.ticker.add(t => lenis.raf(t * 1000))`

### CDN Versions (current as of 2026-03)
- GSAP: 3.13.0
- Lenis: 1.0.42 (studio-freight)
- Three.js: r167 (0.167.1)

