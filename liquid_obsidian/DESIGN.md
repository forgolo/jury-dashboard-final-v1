# Design System Document: Liquid Intelligence

## 1. Overview & Creative North Star
**Creative North Star: "The Digital Observatory"**

This design system is engineered for "Современное предприятие," a jury dashboard that demands the authority of an industrial giant paired with the fluid agility of a digital-first future. We are moving away from the static, "boxed-in" nature of traditional dashboards. Instead, we treat the interface as a **Digital Observatory**: a layered, translucent environment where data floats in a deep, atmospheric space.

The system breaks the "template" look through **atmospheric depth**. By utilizing high-end glassmorphism, noise textures, and intentional asymmetry, we create a UI that feels less like a website and more like a bespoke physical console. We prioritize high-contrast typography and neon light-leaks to ensure that even in a complex jury session, the most critical data points "glow" with priority.

---

## 2. Colors
Our palette is rooted in deep, nocturnal tones, punctuated by high-energy neon signals.

### Surface Hierarchy & Nesting
- **Background (`#0e141d`):** The foundational void. Use a subtle noise texture overlay at 3% opacity to add tactile "soul."
- **Deep Tonal Base:** Use a mix of deep forest greens and dark blues to create "zones" without using borders.
- **The "No-Line" Rule:** 1px solid borders are strictly prohibited for layout sectioning. Boundaries are created through:
    - **Surface Transitions:** Placing a `surface-container-high` card on a `surface-container-low` background.
    - **Ambient Light:** Using a `primary` (cyan) or `secondary` (emerald) soft radial gradient (blur: 150px) behind key glass panels.

### Accent Roles
- **Primary (`#a4e3ff`):** Neon Cyan. Reserved for active states, primary CTAs, and critical progress markers.
- **Secondary (`#46fa9c`):** Forest Neon Green. Used for positive scoring (3 points) and "Success" indicators.
- **The "Glass & Gradient" Rule:** Main CTAs should never be flat. Apply a linear gradient from `primary` to `primary-container` at a 135-degree angle to give buttons a three-dimensional "liquid" feel.

---

## 3. Typography
We utilize **Inter** for its mathematical precision and **SB Sans Display** for authoritative headings.

- **Display & Headline:** Used for project titles and scoring totals. These should feel like "hero" elements. Use `display-lg` with a `-0.02em` letter spacing to create a high-end editorial look.
- **Title & Body:** For descriptions and jury criteria. Use `title-md` for readability.
- **Label:** For metadata (timers, participant IDs). These must always be in `label-md` or `label-sm`, often in uppercase with `+0.05em` tracking for a technical, "data-feed" aesthetic.

**Contrast Strategy:** In dark mode, pure white text can cause "halation" (blurring). Use `on-surface` (`#dde2f0`) for body text and reserve pure `#FFFFFF` only for Display headings and active neon states.

---

## 4. Elevation & Depth
Depth is not an afterthought; it is the primary navigation tool of this system.

- **The Layering Principle:** 
    - **Level 0 (Floor):** `surface` background + Noise Texture.
    - **Level 1 (Sections):** `surface-container-low` (no blur).
    - **Level 2 (Glass Cards):** `surface-container-high` with `backdrop-filter: blur(20px)` and 60% opacity.
- **Ambient Shadows:** Forget "Drop Shadows." Use "Glow Shadows." Floating panels use a 40px blur shadow tinted with the `primary` color at 8% opacity. This creates a "hovering" effect over a light source.
- **The "Ghost Border" Fallback:** For glass panels, use a 1px "Ghost Border" at the top and left edges only. Token: `outline-variant` at 20% opacity. This mimics how light hits the edge of real glass.

---

## 5. Components

### Glass Cards (Frosted Effect)
The centerpiece of the dashboard. 
- **Style:** Background: `surface-container-highest` at 40% opacity; Backdrop-filter: `blur(20px)`.
- **Edge:** 1px ghost border (`#FFFFFF` at 10% opacity).
- **Corner:** `xl` (1.5rem) for a modern, friendly feel.

### Chip-Style Scoring (0-3 Scale)
Interactive elements for the jury.
- **0-1 Points:** `surface-container-lowest` with `on-surface-variant` text.
- **2 Points:** `primary-container` with `on-primary-container` text.
- **3 Points:** `secondary-container` (Green) with a subtle neon outer glow.
- **Interaction:** "Springy" hover effect (Scale: 1.05, Elastic transition).

### Animated Progress Bars (Timers)
- **Track:** `surface-container-highest` (narrow, 4px height).
- **Indicator:** Gradient from `primary` to `secondary`. 
- **Animation:** A "pulse" glow at the leading edge of the progress bar to indicate active counting.

### Buttons
- **Primary:** Gradient fill, `xl` rounding, springy hover.
- **Tertiary:** No background, `primary` text, with a `blur(10px)` glass effect on hover only.

---

## 6. Do's and Don'ts

### Do
- **Do** use intentional asymmetry. Align a large `display-lg` heading to the far left while keeping scoring chips tucked into a glass card on the right.
- **Do** use the noise texture. It eliminates "banding" in dark gradients and adds a premium, analog feel.
- **Do** rely on vertical white space (from the Spacing Scale) rather than dividers to separate jury members in a list.

### Don't
- **Don't** use 100% opaque black. It kills the glassmorphism effect. Always use the `surface` tokens.
- **Don't** use "standard" system shadows. If the shadow isn't tinted or extra-diffused, it doesn't belong in this system.
- **Don't** use sharp 90-degree corners. Everything in "Современное предприятие" must feel fluid; stick to the `md` to `xl` roundedness scale.
- **Don't** use high-contrast white borders. They break the "liquid glass" illusion. Use low-opacity ghost borders.