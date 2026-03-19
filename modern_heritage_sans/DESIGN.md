# Design System Strategy: The Contemporary Monograph

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Contemporary Monograph."** 

We are moving away from the dusty, literal interpretations of "archives" and moving toward the aesthetic of a high-end, digital museum catalog. The goal is to balance the weight of African heritage with the precision of modern Swiss-inspired layout design. 

This design system breaks the "template" look by favoring **intentional asymmetry** and **high-contrast typography scales**. We treat the screen not as a grid of boxes, but as a curated canvas. By utilizing a "Modern Archivist" lens, we use expansive white space (the "Stone" neutrals) to give every artifact, image, and text block the "breathing room" required for a premium, gallery-like experience.

---

## 2. Colors & Surface Philosophy
The palette is rooted in a "Light Stone" foundation, punctuated by a surgical use of Deep Red.

### The Palette
*   **Primary (#8B0000):** This is our signature mark. It must be used sparingly—think of it as a wax seal on a document or a single red thread in a textile. Use it for critical CTAs and active states only.
*   **Neutrals:** We utilize the `surface` and `surface-container` tiers to define the "Stone" environment.
    *   `surface`: The primary "gallery wall" (#fef9ef).
    *   `surface-container-low`: Used for secondary background sections to create a soft, natural shift.

### The "No-Line" Rule
To maintain a high-end editorial feel, **1px solid borders are strictly prohibited for sectioning.** Boundaries must be defined through:
1.  **Background Color Shifts:** Placing a `surface-container-low` section against a `surface` background.
2.  **Intentional Spacing:** Using the `24` (8.5rem) or `20` (7rem) spacing tokens to create a "mental" boundary.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. Use `surface-container-lowest` for the most recessed elements and `surface-container-highest` for the most elevated. 
*   **Example:** A card (`surface-container-highest`) sitting on a container (`surface-container-low`) which sits on the main page (`surface`). This creates depth without visual clutter.

### Signature Textures & Glass
*   **The "Glass" Rule:** Floating navigation or overlay menus must use a semi-transparent `surface` color with a 20px backdrop-blur. This allows the "Heritage" content to bleed through, softening the interface.
*   **Gradients:** For primary CTAs, use a subtle linear gradient from `primary` (#610000) to `primary_container` (#8b0000) at a 135-degree angle. This adds "soul" and prevents the deep red from feeling flat or digital.

---

## 3. Typography: The Editorial Voice
We utilize a dual-sans-serif approach to create a clean, authoritative hierarchy.

*   **Display & Headlines (Manrope):** Manrope’s geometric yet humanist qualities provide the "Modern" in Modern Archivist. Use `display-lg` (3.5rem) with tight letter-spacing (-0.02em) for hero moments to mimic high-end magazine headers.
*   **Titles & Body (Manrope):** Use `body-lg` for long-form reading. The generous x-height ensures readability against the stone backgrounds.
*   **Labels (Inter):** For functional UI (metadata, dates, tags), use `Inter` at `label-sm` (0.6875rem) in all-caps with increased letter-spacing (+0.05em). This provides a "technical" archival contrast to the fluid Manrope headers.

---

## 4. Elevation & Depth
In this design system, depth is a byproduct of light and shadow, not lines.

*   **The Layering Principle:** Rather than using shadows for everything, stack surface tokens. A `surface-container-lowest` card on a `surface-container-low` section creates a soft "set-in" look, perfect for archival entries.
*   **Ambient Shadows:** If an element must float (e.g., a modal or floating action), use a "Tincture Shadow":
    *   Blur: 40px - 60px.
    *   Opacity: 4%-6%.
    *   Color: Use a tinted version of `on-surface` (#1d1c16). Never use pure black.
*   **The "Ghost Border" Fallback:** If a container needs more definition (e.g., in high-density data), use the `outline-variant` token at **15% opacity**. It should be felt, not seen.

---

## 5. Components

### Buttons
*   **Primary:** Background: `primary_container` (#8B0000), Text: `on_primary`. Roundedness: `sm` (0.125rem) for a sharp, architectural look.
*   **Tertiary (Ghost):** No background. Text: `primary`. On hover, a subtle `surface-container-high` background appears.

### Cards & Lists
*   **Forbid Dividers:** Do not use lines to separate list items. Use `spacing-4` (1.4rem) between items. 
*   **Archival Cards:** Use `surface-container-low` backgrounds. Image headers should have a 0.25rem (`DEFAULT`) corner radius to maintain a clean, modern edge.

### Input Fields
*   **Styling:** Use a `surface-container-lowest` background. 
*   **Border:** Only a bottom-border using `outline-variant` at 20% opacity. This mimics a "fill-in-the-blank" archival form rather than a modern "web box."

### Chips
*   **Selection Chips:** Use `surface-container-highest` with `label-md` Inter typography. For active states, use a small 4px `primary` dot next to the text rather than changing the whole background color.

---

## 6. Do’s and Don’ts

### Do:
*   **Use Asymmetric Grids:** Offset images from text blocks to create a curated, editorial flow.
*   **Embrace the Deep Red:** Use the #8B0000 for a single "Hero" element per scroll-depth to keep it premium.
*   **Leverage Typography as Graphic:** Use large `display-md` numbers for dates or counts to act as visual anchors.

### Don't:
*   **Don't use 100% Opaque Borders:** This kills the "Modern Archivist" sophistication.
*   **Don't use Standard Shadows:** Avoid the "drop shadow" look; if it doesn't look like ambient museum lighting, it’s too heavy.
*   **Don't Center Everything:** High-end design lives in the tension of off-center compositions. Keep text left-aligned to `24` (8.5rem) margins.

### Accessibility Note:
Ensure that while our `primary` red is used subtly, it always maintains a contrast ratio of 4.5:1 against the stone backgrounds for essential interactive elements. Use `on-surface-variant` for secondary text to ensure legibility without breaking the monochromatic "stone" harmony.