# Design Taste Frontend: Complete System Document

## Overview
This is a Senior UI/UX Engineering framework designed to override default LLM design biases and enforce metric-based, component-driven architecture with strict CSS hardware acceleration principles.

## 1. Active Baseline Configuration
Three core dials control all design generation:
- **DESIGN_VARIANCE: 8** (1=Symmetry, 10=Chaos)
- **MOTION_INTENSITY: 6** (1=Static, 10=Cinematic)
- **VISUAL_DENSITY: 4** (1=Airy, 10=Packed Data)

Users may override these values dynamically via chat prompts.

## 2. Default Architecture & Conventions

**Dependency Verification:** Check `package.json` before importing any third-party library. Output installation commands if missing.

**Framework:** React/Next.js with Server Components (RSC) as default. Wrap providers in `"use client"` components for global state management.

**State Management:** Local `useState`/`useReducer` for isolated UI; global state only for deep prop-drilling avoidance.

**Styling:** Tailwind CSS (v3/v4). Check `package.json` for version compatibility. No `postcss` plugin in v4; use `@tailwindcss/postcss` instead.

**Anti-Emoji Policy:** "NEVER use emojis in code, markup, text content, or alt text." Replace with Radix, Phosphor icons, or SVG primitives.

**Responsiveness:** Use `min-h-[100dvh]` for full-height sections (not `h-screen`). Grid over flexbox math. Standardize breakpoints (`sm`, `md`, `lg`, `xl`).

**Icons:** Use `@phosphor-icons/react` or `@radix-ui/react-icons` exclusively. Standardize `strokeWidth` globally.

## 3. Design Engineering Directives (Bias Correction)

**Rule 1 - Deterministic Typography:**
- Display: `text-4xl md:text-6xl tracking-tighter leading-none`
- Avoid Inter font; use Geist, Outfit, Cabinet Grotesk, or Satoshi
- Serif fonts banned for Dashboard/Software UIs
- Body: `text-base text-gray-600 leading-relaxed max-w-[65ch]`

**Rule 2 - Color Calibration:**
- Max 1 accent color, saturation < 80%
- "AI Purple/Blue" aesthetic strictly banned
- Use neutral bases (Zinc/Slate) with singular high-contrast accents
- Maintain one palette throughout

**Rule 3 - Layout Diversification:**
- "Centered Hero sections strictly BANNED when DESIGN_VARIANCE > 4"
- Force Split Screen, Left-Aligned content, or Asymmetric White-space

**Rule 4 - Materiality & Anti-Card Overuse:**
- "For VISUAL_DENSITY > 7, generic card containers are strictly BANNED"
- Use logic-grouping via `border-t`, `divide-y`, or negative space
- Cards only when elevation is functionally required

**Rule 5 - Interactive UI States:**
- Implement complete interaction cycles: Loading, Empty States, Error States
- Use `-translate-y-[1px]` or `scale-[0.98]` for tactile feedback

**Rule 6 - Data & Form Patterns:**
- Label above input, error text below, `gap-2` for input blocks

## 4. Creative Proactivity (Anti-Slop Implementation)

**Liquid Glass Refraction:** Add 1px inner border (`border-white/10`) and subtle inner shadow (`shadow-[inset_0_1px_0_rgba(255,255,255,0.1)]`).

**Magnetic Micro-physics (MOTION_INTENSITY > 5):** Use Framer Motion's `useMotionValue` and `useTransform`—never React `useState` for continuous animations.

**Perpetual Micro-Interactions:** Embed infinite animations (Pulse, Typewriter, Float, Shimmer, Carousel) with "premium Spring Physics (`type: "spring", stiffness: 100, damping: 20`)".

**Layout Transitions:** Utilize Framer Motion's `layout` and `layoutId` props for smooth state changes.

**Staggered Orchestration:** Use `staggerChildren` or CSS cascade for sequential reveals. Parent and Children must reside in identical Client Component tree.

## 5. Performance Guardrails

- Apply grain/noise filters exclusively to fixed, `pointer-event-none` pseudo-elements
- Never animate `top`, `left`, `width`, `height`—use `transform` and `opacity`
- Z-indexes strictly for systemic contexts (Sticky Navbars, Modals, Overlays)

## 6. Technical Reference (Dial Definitions)

**DESIGN_VARIANCE (1-10):**
- 1-3: Centered, symmetrical grids
- 4-7: Overlapping elements, varied aspect ratios, offset headers
- 8-10: Masonry, fractional grids, asymmetric spacing; MOBILE OVERRIDE to single-column below `md:`

**MOTION_INTENSITY (1-10):**
- 1-3: CSS `:hover` and `:active` only
- 4-7: `transition: all 0.3s cubic-bezier(0.16, 1, 0.3, 1)`, `animation-delay` cascades
- 8-10: Scroll-triggered reveals, Framer Motion hooks (no `window.addEventListener('scroll')`)

**VISUAL_DENSITY (1-10):**
- 1-3: Lots of white space, expensive/clean
- 4-7: Normal spacing for standard apps
- 8-10: "Tiny paddings. No card boxes; just 1px lines. Everything packed."

## 7. AI Tells (Forbidden Patterns)

**Visual & CSS:**
- NO neon/outer glows
- NO pure black (#000000); use Off-Black, Zinc-950, or Charcoal
- NO oversaturated accents
- NO excessive gradient text
- NO custom mouse cursors

**Typography:**
- NO Inter font
- NO oversized H1s
- Serif only for creative/editorial designs

**Layout & Spacing:**
- Ensure mathematical precision in padding/margins
- NO 3-column card layouts; use Zig-Zag, asymmetric grid, or horizontal scroll

**Content & Data:**
- NO generic names (John Doe, Sarah Chan)
- NO generic avatars (standard SVG egg icons)
- NO predictable fake numbers (99.99%, 50%); use organic data (47.2%)
- NO startup slop names (Acme, Nexus, SmartFlow)
- NO AI clichés (Elevate, Seamless, Unleash, Next-Gen)

**External Resources:**
- NO broken Unsplash links; use `https://picsum.photos/seed/{random_string}/800/600`
- shadcn/ui must be heavily customized (radii, colors, shadows)

## 8. The Creative Arsenal (High-End Inspiration)

Advanced concepts library (GSAP ScrollTrigger/Parallax, ThreeJS/WebGL):
- **Never mix GSAP/ThreeJS with Framer Motion** in same component tree
- Default to Framer Motion for UI/Bento interactions
- Use GSAP/ThreeJS exclusively for isolated full-page scrolltelling

### Navigation & Menus
Mac OS Dock Magnification, Magnetic Button, Gooey Menu, Dynamic Island, Contextual Radial Menu, Floating Speed Dial, Mega Menu Reveal

### Layout & Grids
Bento Grid, Masonry, Chroma Grid, Split Screen Scroll, Curtain Reveal

### Cards & Containers
Parallax Tilt Card, Spotlight Border Card, Glassmorphism Panel, Holographic Foil Card, Tinder Swipe Stack, Morphing Modal

### Scroll-Animations
Sticky Scroll Stack, Horizontal Scroll Hijack, Locomotive Scroll Sequence, Zoom Parallax, Scroll Progress Path, Liquid Swipe Transition

### Galleries & Media
Dome Gallery, Coverflow Carousel, Drag-to-Pan Grid, Accordion Image Slider, Hover Image Trail, Glitch Effect Image

### Typography & Text
Kinetic Marquee, Text Mask Reveal, Text Scramble Effect, Circular Text Path, Gradient Stroke Animation, Kinetic Typography Grid

### Micro-Interactions & Effects
Particle Explosion Button, Liquid Pull-to-Refresh, Skeleton Shimmer, Directional Hover Aware Button, Ripple Click Effect, Animated SVG Line Drawing, Mesh Gradient Background, Lens Blur Depth

## 9. The "Motion-Engine" Bento Paradigm

Modern SaaS dashboard/feature section architecture:

**Core Design Philosophy:**
- High-end, minimal, functional
- Background: `#f9fafb`
- Cards: pure white with `border-slate-200/50` (1px border)
- Surfaces: `rounded-[2.5rem]` with diffusion shadow `shadow-[0_20px_40px_-15px_rgba(0,0,0,0.05)]`
- Typography: Geist, Satoshi, Cabinet Grotesk with `tracking-tight`
- Labels outside/below cards
- Padding: `p-8` or `p-10`

**Animation Engine Specs:**
- Spring Physics: "No linear easing. Use `type: "spring", stiffness: 100, damping: 20`"
- `layout` and `layoutId` props for smooth transitions
- Infinite loops for "alive" dashboards
- Memoize perpetual motion in isolated Client Components

**5-Card Archetypes:**
1. The Intelligent List (auto-sorting with `layoutId`)
2. The Command Input (Typewriter Effect)
3. The Live Status (breathing indicators, pop-up notifications)
4. The Wide Data Stream (seamless Infinite Carousel)
5. The Contextual UI (staggered highlights, floating action toolbar)

## 10. Final Pre-Flight Check

- [ ] Global state avoids deep prop-drilling
- [ ] Mobile layout collapse guaranteed for high-variance designs
- [ ] Full-height sections use `min-h-[100dvh]`
- [ ] `useEffect` animations contain cleanup functions
- [ ] Empty, loading, error states provided
- [ ] Cards omitted where spacing suffices
- [ ] CPU-heavy perpetual animations isolated in Client Components

---

This framework serves as a comprehensive design and engineering ruleset to produce premium, non-generic digital interfaces with strict adherence to performance, accessibility, and visual hierarchy principles.
