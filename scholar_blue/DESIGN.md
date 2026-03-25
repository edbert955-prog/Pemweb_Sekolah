# Design System Document: The Scholarly Editorial

## 1. Overview & Creative North Star
**Creative North Star: The Academic Curator**
This design system moves away from the "institutional grid" and toward a high-end editorial experience. It treats educational content not as data, but as a prestigious narrative. By utilizing intentional asymmetry, expansive negative space, and a sophisticated layering of whites and grays, we create an environment that feels both authoritative and breathable. 

The system breaks the "template" look by overlapping text elements across container boundaries and using high-contrast typography scales—pairing the geometric precision of **Manrope** for displays with the functional clarity of **Inter** for utility.

## 2. Colors
Our palette is rooted in a deep, "Oxford" blue, supported by a sophisticated range of neutral surfaces that prioritize depth over decoration.

*   **Primary (#005bbf) & Primary Container (#1a73e8):** These are our "Trust Tokens." Use the Primary for high-action items and the Container for hero backgrounds to establish an immediate sense of professional stability.
*   **The "No-Line" Rule:** 1px solid borders are strictly prohibited for sectioning. Boundaries must be defined solely through background shifts. For example, a `surface-container-low` section should sit directly against a `surface` background to denote a change in context.
*   **Surface Hierarchy & Nesting:** Treat the UI as physical layers of fine paper. 
    *   **Level 0:** `surface` (The base canvas).
    *   **Level 1:** `surface-container-low` (Secondary content blocks).
    *   **Level 2:** `surface-container-lowest` (Interactive cards or "floating" editorial notes).
*   **The "Glass & Gradient" Rule:** For the sticky navbar and floating staff profiles, utilize Glassmorphism. Use `surface_container_lowest` at 80% opacity with a `backdrop-blur` of 12px.
*   **Signature Textures:** For the Hero CTA, apply a subtle linear gradient from `primary` to `primary_container` (135° angle). This adds a "soul" to the button that flat color cannot replicate.

## 3. Typography
We employ a "Large-Scale Editorial" approach to typography, creating a clear hierarchy between inspiration and information.

*   **Display & Headlines (Manrope):** These are our "Voice." Use `display-lg` for hero sections with tight letter-spacing (-0.02em) to create a bold, modern impact.
*   **Titles & Body (Inter):** These are our "Logic." `body-lg` is the workhorse for narrative text, while `label-md` is reserved for metadata and micro-copy.
*   **The Brand Identity:** The juxtaposition of the wide, round Manrope headlines against the tall, rhythmic Inter body text conveys a brand that is both visionary and meticulously organized.

## 4. Elevation & Depth
In this system, "elevation" is a feeling, not a shadow.

*   **The Layering Principle:** Avoid shadows for static cards. Instead, place a `surface-container-lowest` (pure white) card on a `surface-container-low` (#f3f4f5) background. The subtle contrast creates a "soft lift."
*   **Ambient Shadows:** If a component must float (e.g., a modal or a primary dropdown), use an extra-diffused shadow: `box-shadow: 0 20px 40px rgba(25, 28, 29, 0.06)`. Note the low opacity; it should feel like natural ambient light.
*   **The "Ghost Border" Fallback:** If accessibility requires a border, use `outline-variant` at 20% opacity. Never use 100% opaque borders.
*   **Glassmorphism:** Use semi-transparent surface tokens for the sticky navbar. This ensures the hero imagery bleeds through slightly, preventing the UI from feeling "pasted" on top of the content.

## 5. Components

### Navigation & Hero
*   **Sticky Navbar:** `surface_container_lowest` at 85% opacity with `backdrop-blur`. No bottom border; use a very subtle `ambient shadow` only when scrolled.
*   **Hero Section:** Use `display-lg` text. Offset the sub-headline by `spacing-8` to the right to create intentional asymmetry.

### Buttons & Chips
*   **Primary Button:** `primary` background with `on_primary` text. `rounded-md` (0.375rem). Use the "Signature Texture" gradient on hover.
*   **Tertiary Button:** No background or border. Use `primary` text with an underline that only appears on hover.
*   **Chips:** Use `surface-container-high` for backgrounds. No borders.

### Staff Profile Cards
*   **Styling:** Forbid dividers. Use a `surface-container-lowest` card. The profile image should be slightly desaturated, returning to full color only on hover.
*   **Layout:** Name in `title-lg`, role in `label-md` using the `secondary` color token.

### Modern Forms
*   **Input Fields:** `surface-container-highest` background. No border, only a 2px bottom "focus line" in `primary` when active.
*   **Validation:** Use `error` for text and `error_container` for the input background during an error state.

### Relevant School Components
*   **Event Calendar Rows:** Use alternating `surface` and `surface-container-low` backgrounds instead of lines.
*   **Admission Progress Tracker:** A thick 8px track using `surface-container-highest` with a `primary` fill.

## 6. Do's and Don'ts

### Do
*   **Do** use the `24` (6rem) spacing token between major editorial sections to let the design "breathe."
*   **Do** overlap elements. Let a staff photo "break" the container of a background color block to create depth.
*   **Do** use `on_surface_variant` for body text to reduce harsh contrast against pure white, increasing readability.

### Don't
*   **Don't** use 1px dividers to separate list items. Use `spacing-4` of vertical white space instead.
*   **Don't** use pure black (#000) for text. Always use `on_surface` (#191c1d).
*   **Don't** use standard "drop shadows." If it doesn't look like a soft glow, it’s too heavy.