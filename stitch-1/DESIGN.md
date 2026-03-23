# Design System Document: The Sun-Drenched Editorial

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Sun-Drenched Editorial."** This concept moves beyond the standard "coffee shop app" aesthetic to create a digital space that feels like a premium lifestyle magazine. It is high-end, intentional, and warm. 

We break the traditional "template" look by utilizing heavy asymmetric layouts, overlapping high-quality Brazilian coffee imagery with typography, and leaning into large "white space" (using our cream `surface` color). The goal is to make the young professional feel they are interacting with a curated experience, not just a utility. Every transition should feel like turning a heavy, matte-coated page.

---

## 2. Colors & Tonal Depth
The palette is rooted in the warmth of Brazilian earth and the sophistication of modern minimalism.

*   **Primary (`#8f490e`):** Our terracotta. This is used sparingly for high-impact actions and brand signifiers.
*   **Surface & Background (`#fcf9f3`):** This off-white/cream is the canvas. It provides a softer, more premium feel than pure white.
*   **Typography (`#1c1c18`):** A deep charcoal that provides high contrast without the harshness of pure black.

### The "No-Line" Rule
**Explicit Instruction:** 1px solid borders are strictly prohibited for sectioning. We do not use lines to separate content. Boundaries must be defined solely through background color shifts. For example, a featured pastry section might sit on `surface-container-low` to distinguish it from the main `surface` background.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. To create depth:
1.  **Base Layer:** `surface`
2.  **Sectional Shift:** `surface-container-low` (use for large background blocks).
3.  **Component Lift:** `surface-container-lowest` (use for cards to make them appear "closer" to the user).

### The "Glass & Gradient" Rule
To add "soul" to the minimalist layout, use subtle linear gradients on Primary CTAs, transitioning from `primary` to `primary_container`. For floating navigation or overlays, use **Glassmorphism**: apply `surface` colors at 80% opacity with a `16px` to `24px` backdrop-blur.

---

## 3. Typography: The Editorial Voice
We use **Manrope** exclusively. Its geometric yet humanist qualities bridge the gap between professional and youthful.

*   **Display (Display-lg, Display-md):** Used for "Hero" moments. These should often be placed with negative letter-spacing (-0.02em) and occasionally overlapped by high-quality imagery of coffee beans or latte art.
*   **Headlines (Headline-lg to Headline-sm):** Clear, authoritative, and always set in `on_surface`.
*   **Body (Body-lg, Body-md):** Maximum readability. Use `body-lg` for lead paragraphs to maintain the editorial feel.
*   **Labels (Label-md, Label-sm):** Used for secondary metadata (e.g., origin of beans, tasting notes).

---

## 4. Elevation & Depth
We eschew traditional Material shadows in favor of **Tonal Layering**.

### The Layering Principle
Depth is achieved by "stacking" the `surface-container` tiers. A `surface-container-lowest` card placed on a `surface-container` section creates a soft, natural lift that feels architectural rather than digital.

### Ambient Shadows
If a floating element (like a FAB or a modal) requires a shadow, it must be an **Ambient Shadow**:
*   **Blur:** 32px to 64px.
*   **Opacity:** 4%–6%.
*   **Color:** Use a tinted version of `on-surface` (`#1c1c18`) to mimic natural light falling on a warm surface.

### The "Ghost Border" Fallback
If accessibility requires a container edge, use a **Ghost Border**: the `outline-variant` token at 15% opacity. Never use 100% opaque borders.

---

## 5. Components

### Buttons
*   **Primary:** High-pill shape (`rounded-full`). Background is a subtle gradient of `primary`. Typography is `on_primary` (White).
*   **Secondary:** No fill. Use a `surface-container-high` background on hover. Typography is `primary`.
*   **Tertiary:** Purely typographic with a `primary` underline that appears on hover.

### Cards & Imagery
*   **Imagery:** Use large-scale, high-contrast photos of Brazilian coffee culture. Images should have a subtle `xl` (0.75rem) corner radius.
*   **Card Structure:** No dividers. Separate the title, description, and price using the Spacing Scale (e.g., `spacing-4` between elements). Use background shifts (`surface-container-low`) to group related items.

### Input Fields
*   **Styling:** Use `surface-container` as the base fill. No bottom line.
*   **Focus State:** The background shifts to `surface-container-highest` with a `primary` label.

### Chips (Selection)
*   Used for coffee roast levels or pastry categories. Use `secondary_container` for unselected states and `primary` with `on_primary` for selected states.

### Lists
*   **The Divider Ban:** Strictly forbid 1px dividers between list items. Instead, use `spacing-6` to create clear vertical rhythm and "breathing room" for the content.

---

## 6. Do's and Don'ts

### Do
*   **Do** use asymmetrical layouts where text is left-aligned and imagery is right-aligned with an intentional overlap.
*   **Do** lean into the Spacing Scale. Use `spacing-16` or `spacing-20` for section margins to create a premium, uncrowded feel.
*   **Do** use high-quality, warm-toned photography that complements the terracotta (`primary`) and cream (`surface`) palette.

### Don't
*   **Don't** use "Card Shadows" for every element. Rely on background color shifts first.
*   **Don't** use standard 1px grey lines. They break the "editorial paper" illusion.
*   **Don't** use center-alignment for long-form text. Editorial design thrives on strong left-aligned axes.
*   **Don't** use bright, saturated colors outside the defined palette. The vibe must remain grounded and sophisticated.