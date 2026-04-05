# Design System Strategy: The Sommelier’s Digital Cellar

## 1. Overview & Creative North Star
**Creative North Star: "The Curated Vintage"**
This design system is not a utility; it is a digital estate. We are moving away from the "template" look of modern e-commerce toward a high-end editorial experience. The goal is to evoke the sensory journey of a private cellar tour—low light, rich textures, and an obsession with detail.

To break the rigid digital grid, we employ **Intentional Asymmetry**. Images should bleed off-canvas, and typography should overlap container boundaries to create a sense of movement. We avoid the "boxed-in" feel of standard layouts by using expansive white (or dark) space, ensuring every element feels placed by a curator’s hand rather than a developer’s grid.

## 2. Colors: Tonal Depth & Liquid Radiance
Our palette is rooted in the deep, organic tones of aging wine and polished gold. We use a dark-mode-first approach to emphasize exclusivity and luxury.

### The Palette (Material Design Mapping)
*   **Primary (Wine):** `#ffb3ad` (Primary) / `#4a0e0e` (Primary Container). The deep red is our heritage; use it for focal sections and key calls to action.
*   **Secondary (Gold):** `#e9c349` (Secondary). This is our "Liquid Light." Use it sparingly for interactive highlights and gold glows.
*   **Surface Hierarchy:** 
    *   `surface` (`#131313`): The base canvas.
    *   `surface-container-low` (`#1c1b1b`): Subtle sectioning.
    *   `surface-container-highest` (`#353535`): Elevated components like cards or menus.

### The "No-Line" Rule
**Lines are prohibited for sectioning.** To define boundaries between content blocks, use background color shifts. For example, a hero section on `surface` should transition into a product gallery on `surface-container-low`. The transition is the boundary.

### Signature Textures & Glassmorphism
To achieve a "modern twist," we utilize **Glassmorphism**. Overlays, navigation bars, and floating cards must use semi-transparent `surface` colors with a `backdrop-filter: blur(20px)`. This allows the rich photography of vineyards and spirits to "bleed through" the UI, creating an immersive, layered depth.

## 3. Typography: Editorial Authority
The typography system relies on the tension between the classical `notoSerif` (Headings) and the architectural `manrope` (Body).

*   **Display (notoSerif):** High-contrast, large-scale serif. Use `display-lg` (3.5rem) for vintage titles or brand statements. It should feel like a masthead.
*   **Body (manrope):** Use `body-lg` (1rem) for tasting notes and storytelling. The generous line height (minimum 1.6) is essential for readability and a premium feel.
*   **Labels (manrope):** `label-md` (0.75rem) should always be in **ALL CAPS** with increased letter spacing (0.1em) to denote "Artisanal" metadata like ABV, Year, or Region.

## 4. Elevation & Depth: Tonal Layering
Traditional drop shadows are too "digital." We create depth through physical metaphors.

*   **The Layering Principle:** Instead of shadows, stack surface tiers. Place a `surface-container-highest` card on a `surface` background. The subtle shift in gray-black is enough to signify elevation.
*   **Ambient Shadows:** If a floating element (like a mobile menu) requires a shadow, use a large blur radius (40px+) and a very low opacity (6%) tinted with the `primary` wine red. It should look like a soft glow, not a dark stain.
*   **The "Ghost Border" Fallback:** If a container needs definition against a similar background, use a 1px border with `outline-variant` at **15% opacity**. It should be felt, not seen.

## 5. Components: The Artisanal Toolkit

### Buttons (The "Seal of Quality")
*   **Primary:** A solid fill of `primary-container` (`#4a0e0e`) with `on-primary-container` text. Use the `DEFAULT` (0.25rem) roundedness for a sharp, sophisticated edge.
*   **Secondary:** An "Outline" button using the Ghost Border rule. No solid background.
*   **Tertiary:** Text-only in `secondary` (Gold) with a subtle `secondary-fixed-dim` underline that expands on hover.

### Cards & Lists (The Gallery Approach)
*   **No Dividers:** Forbid the use of horizontal rules. Use vertical whitespace (padding-bottom: 4rem) to separate items.
*   **Product Cards:** Use a background of `surface-container-low`. The product image should be centered with a subtle `secondary` gold glow behind the bottle to mimic light hitting glass.

### Input Fields (The Registry)
*   **Style:** Minimalist. Only a bottom border using `outline`. On focus, the border transitions to `secondary` (Gold).
*   **Labeling:** Labels should use `label-sm` and remain visible above the input to maintain an organized, "archival" look.

### Specialty Component: The "Vintage Picker"
A custom horizontal scroll component for selecting years. It uses `display-sm` typography, where the active year is in `secondary` gold and inactive years are `on-surface-variant` with 40% opacity.

## 6. Do's and Don'ts

### Do
*   **Do** use large amounts of "breathing room" (Spacing scale: 64px, 80px, 120px).
*   **Do** use high-resolution photography with warm, "golden hour" lighting.
*   **Do** allow elements to overlap (e.g., a bottle image overlapping a `display-lg` heading).

### Don't
*   **Don't** use 100% black (#000000). Use `surface` (#131313) to keep the shadows "soft."
*   **Don't** use fully rounded (pill) buttons. It feels too "tech" and "startup." Stick to the `DEFAULT` (4px) or `none` (0px) for a more architectural feel.
*   **Don't** use standard "Success" green or "Warning" orange. If necessary, use muted tones that fit the palette (e.g., a sage green for success).

### Accessibility Note
Ensure that all `secondary` gold text on `surface` backgrounds meets WCAG AA standards. If the gold is too light, reserve it for decorative elements and use `on-surface` for critical functional text.