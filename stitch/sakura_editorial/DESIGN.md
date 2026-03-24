# Design System Strategy: Editorial Ethereal

## 1. Overview & Creative North Star
**Creative North Star: The Celestial Editorial**
This design system moves beyond the standard SaaS "blocks and lines" approach, drawing inspiration from high-end Japanese fashion periodicals and the luminous, atmospheric depth of modern 2D animation. It is a world where white space isn't just "empty," but serves as a canvas for light. 

By merging the clean, structured discipline of modern typography with the soft, vibrant energy of "Sakura" pinks and "Zenith" blues, we create an experience that feels both youthful and authoritative. The design breaks the grid through intentional asymmetry—overlapping glass layers, offset text headers, and floating elements that mimic cherry blossoms drifting in the wind. This is not just a UI; it is a curated digital atmosphere.

---

## 2. Colors & Surface Philosophy
The palette utilizes high-chroma pastels anchored by deep, ink-like energetic tones to ensure readability remains paramount.

### The "No-Line" Rule
**Lines are prohibited for sectioning.** To define boundaries, designers must rely on background color shifts. A section intended to be distinct should transition from `surface` (`#fbf9fa`) to `surface-container-low` (`#f5f3f4`). This creates a soft, sophisticated transition that feels like high-quality paper stock rather than a digital wireframe.

### Surface Hierarchy & Nesting
Treat the UI as a physical stack of semi-translucent sheets. 
- **Base Level:** `surface`
- **Secondary Content:** `surface-container-low`
- **Interactive Cards/Modals:** `surface-container-lowest` (pure white) nested inside lower tiers to create a "natural lift."
- **Glassmorphism:** For floating navigation or top-level overlays, use `surface` at 70% opacity with a `20px` backdrop-blur. This allows the vibrant `primary` (`#ac2d5e`) and `secondary` (`#006789`) accents to bleed through the UI, softening the overall aesthetic.

### Signature Textures
Main CTAs and Hero sections should avoid flat fills. Use a subtle linear gradient from `primary` (`#ac2d5e`) to `primary-container` (`#ffa8c0`) at a 135-degree angle. This mimics the light-play found in anime cel-shading, providing a "glow" that feels intentional and premium.

---

## 3. Typography
The system uses a dual-type approach to balance energy with editorial precision.

- **The Display & Headline Voice:** `Manrope` is the protagonist. At large scales (`display-lg` at 3.5rem), it should be set with tight letter-spacing (-0.02em) to feel like a magazine masthead. These elements should often be placed with generous, asymmetric padding (e.g., `spacing-12` on one side, `spacing-24` on the other).
- **The Label Voice:** `Plus Jakarta Sans` is used for high-utility labels. Its slightly wider stance provides a modern, tech-forward contrast to the more vertical `Manrope`.
- **Hierarchy as Identity:** Use `primary` for `title-lg` elements to draw the eye, while keeping `body-lg` in `on-surface-variant` (`#5e5f61`) to ensure the page feels airy and light.

---

## 4. Elevation & Depth
In this system, depth is a result of light and opacity, not structural heavy-handedness.

- **Tonal Layering:** Instead of shadows, use `surface-container` tiers. A `surface-container-highest` (`#e2e2e4`) element placed against a `surface` background provides all the "elevation" needed for secondary information.
- **Ambient Shadows:** For high-priority floating elements (like a "Buy" button or a floating nav), use a shadow: `offset-y: 12px, blur: 32px, color: rgba(172, 45, 94, 0.08)`. Notice the color—it’s a tint of the `primary` token, not grey. This creates a "colored light" effect consistent with the anime inspiration.
- **The Ghost Border Fallback:** If a container sits on a background of the same color, use `outline-variant` (`#b1b2b4`) at **15% opacity**. It should be felt, not seen.
- **Corner Radii:** Use `xl` (`1.5rem`) for large containers and `full` (`9999px`) for interactive chips/buttons to maintain the youthful, "soft-edge" 2D aesthetic.

---

## 5. Components

### Buttons
- **Primary:** Gradient fill (`primary` to `primary-container`), `full` roundedness, `Manrope` Bold.
- **Secondary:** `surface-container-lowest` with a `Ghost Border`.
- **Tertiary:** Pure text using `primary` color, 0.5rem underline using `primary-fixed-dim` at 40% opacity.

### Floating Cards (The Anime "Cell")
Cards must never have borders. Use `surface-container-lowest` with a `xl` radius and the Ambient Shadow. For content separation within the card, use `spacing-6` (2rem) of vertical white space instead of divider lines.

### Inputs
Text fields use `surface-container-high` with a bottom-only `outline` token (2px) that transforms into a `primary` gradient on focus. This mimics editorial underlining.

### Glass Tooltips
Use `surface-container-highest` at 80% opacity with `backdrop-filter: blur(8px)`. Keep the text `on-surface` for maximum contrast.

---

## 6. Do’s and Don’ts

### Do
- **Do** use `spacing-16` and `spacing-20` to push content away from edges; embrace the "void."
- **Do** overlap elements. Let a `title-lg` partially sit over a `secondary-container` image to create depth.
- **Do** use `primary-container` (`#ffa8c0`) as a soft background highlight for important text spans.

### Don’t
- **Don’t** use 1px solid black or grey borders. This instantly kills the "Ethereal" look.
- **Don’t** use pure black (`#000000`) for text. Stick to `on-background` (`#313334`) to keep the "ink-on-paper" feel.
- **Don’t** crowd the interface. If you feel the need for a divider line, add `spacing-8` of white space instead.
- **Don't** use standard "drop shadows." If it doesn't look like a soft glow, it doesn't belong.

---

## 7. Spacing Utility Reference
- **Micro-interactions:** `1` (0.35rem) to `2` (0.7rem)
- **Component Padding:** `3` (1rem) to `4` (1.4rem)
- **Section Gaps:** `8` (2.75rem) to `12` (4rem)
- **Hero Margins:** `20` (7rem) +