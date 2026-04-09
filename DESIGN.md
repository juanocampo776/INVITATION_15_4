# Design System Strategy: The Ethereal Manuscript

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Ethereal Manuscript."** 

We are not building a standard event landing page; we are crafting a digital heirloom that feels as though it was pulled from a misty, enchanted woodland. To achieve a high-end editorial feel, the design system must break away from the "boxy" nature of the web. We will utilize **intentional asymmetry**, where text and imagery overlap to create a sense of depth, and a **high-contrast typography scale** that pits sweeping, romantic serifs against hyper-clean, modern sans-serifs. The goal is to move the user through a narrative journey, using white space as a breathing lung and subtle motion to mimic the flickering of fairy lights.

## 2. Colors & Surface Philosophy
This design system utilizes a palette of botanical greens, mystical purples, and sunset pinks, anchored by a warm, paper-like neutral.

### The "No-Line" Rule
Standard 1px borders are strictly prohibited for sectioning. They feel clinical and "templated." Instead, boundaries must be defined through **Background Color Shifts**. For example, a section using `surface-container-low` (#f4f4f0) should sit against a `surface` (#faf9f6) background. This creates a soft, organic transition that feels like layers of fine vellum paper.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. Use the `surface-container` tiers to create depth:
*   **Base Layer:** `surface` (#faf9f6) for the main page scroll.
*   **Secondary Content:** `surface-container` (#eeeeea) for section backgrounds.
*   **Interactive Cards:** `surface-container-lowest` (#ffffff) to provide a "lifted" feel for high-importance items like RSVP forms or Map modules.

### The "Glass & Gradient" Rule
To capture the "misty forest" aesthetic, use **Glassmorphism** for floating elements (e.g., sticky headers or hovering photo frames). Use `surface` colors at 60-80% opacity with a `backdrop-filter: blur(12px)`. 
For CTAs and Hero accents, use subtle gradients transitioning from `primary` (#6d548c) to `primary_container` (#dbbdfd) to mimic the way light filters through a canopy of trees.

## 3. Typography
The typography is a dialogue between tradition (`notoSerif`) and modernity (`manrope`).

*   **Display & Headlines (`notoSerif`):** Used for the Quinceañera’s name, titles, and emotional hooks. These should be set with generous tracking and sometimes italicized to lean into the "whimsical" nature of the forest.
*   **Body & Labels (`manrope`):** Used for all functional information (dates, locations, instructions). This ensures the "magical" style never compromises readability.
*   **Hierarchy Note:** Use `display-lg` (3.5rem) for the hero section, but drop immediately to `body-md` (0.875rem) for subtext. This extreme contrast is a hallmark of high-end editorial design.

## 4. Elevation & Depth
We eschew traditional shadows in favor of **Tonal Layering**.

*   **The Layering Principle:** Place a `surface-container-lowest` card on top of a `surface-container-low` section. The slight shift in hex value provides a natural "lift" that mimics ambient forest light.
*   **Ambient Shadows:** If a floating effect is required for a modal or a primary button, use an extra-diffused shadow.
    *   *Shadow Property:* `box-shadow: 0 20px 40px rgba(48, 51, 48, 0.06);` (Using a 6% opacity of the `on_surface` color). This creates a soft glow rather than a harsh drop-shadow.
*   **The Ghost Border Fallback:** If accessibility requires a stroke (e.g., on an input field), use `outline-variant` (#b1b2af) at 20% opacity. Never use 100% opaque lines.
*   **Golden Accents:** Use the `surface_tint` (#6d548c) or `tertiary_fixed` (#ffb6c1) sparingly as thin "threads" or decorative floral flourishes to suggest golden light.

## 5. Components

### Buttons
*   **Primary:** Pill-shaped (`rounded-full`), using a subtle gradient from `primary` to `primary_dim`. Text should be `on_primary` in `label-md`.
*   **Secondary:** `surface-container-lowest` with a "Ghost Border."
*   **States:** On hover, primary buttons should increase their backdrop-blur or slightly shift toward `primary_fixed_dim` to simulate a "glowing" effect.

### Cards & Lists
*   **The "No Divider" Rule:** Forbid the use of horizontal lines. Use the Spacing Scale (32px - 64px) to separate content items within a card.
*   **Visual Separation:** In lists (like a gift registry), use alternating background colors between `surface` and `surface-container-low` rather than lines.

### Input Fields
*   **Style:** Minimalist. Only a bottom-weighted "Ghost Border" or a soft `surface-container-highest` background.
*   **Focus State:** The border transitions to `primary` (#6d548c) with a soft outer glow of the same color at 10% opacity.

### Signature Component: The "Mist" Carousel
For the photo gallery, images should not have hard corners. Use `rounded-xl` (3rem) and apply a subtle `mask-image` linear gradient that fades the edges slightly into the `surface` background, making the photos feel like they are emerging from a misty forest.

## 6. Do's and Don'ts

### Do
*   **Do** use asymmetrical layouts. Let a heading overlap an image by 20px to create depth.
*   **Do** use `primary_container` (#dbbdfd) as a highlight color for text selections or hover states.
*   **Do** ensure all "magical" elements (fairy lights, floral patterns) are handled as background SVG assets with `pointer-events: none`.

### Don'ts
*   **Don't** use pure black (#000000) for text. Always use `on_surface` (#303330) to maintain a soft, premium feel.
*   **Don't** use `rounded-none`. Everything in an enchanted forest is organic; use a minimum of `rounded-sm` for even the smallest elements.
*   **Don't** clutter the screen. If the user feels "crowded," increase the vertical spacing using the `surface` background to "reset" the eye.