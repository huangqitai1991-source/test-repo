# Design System Strategy: The Cyber-Light Workspace

## 1. Overview & Creative North Star
**Creative North Star: "Luminous Precision"**

This design system moves beyond the standard SaaS template to create a high-end, editorial-grade workspace experience. It rejects the "boxy" nature of traditional booking apps in favor of a "Luminous Precision" aesthetic—an atmosphere that feels surgically clean yet ethereal.

We achieve this through **Atmospheric Asymmetry**. By avoiding rigid, centered grids and instead utilizing intentional white space and overlapping glass layers, we create a sense of forward-looking professionalism. The system feels "Cyber" not through dark modes and neon, but through high-contrast typography, technical precision, and a "light-speed" airy feel that prioritizes focus and mental clarity.

---

## 2. Colors & Surface Philosophy
The palette is rooted in a clinical white base, energized by a high-frequency Electric Purple.

### Palette Strategy
*   **Primary (`#8127cf`):** Our "Electric" pulse. Used sparingly for critical action paths and active states.
*   **Surface Containers:** We use a hierarchy of cool-toned greys (`#f8f9fb` to `#e1e2e4`) to define functional zones without the need for structural lines.
*   **Tertiary (`#7b5500`):** A sophisticated ochre used strictly for "human" elements—warm alerts or specialized highlighting—to prevent the UI from feeling too cold.

### The "No-Line" Rule
Designers are prohibited from using 1px solid borders to section off content. Boundaries must be defined solely through background color shifts. For example, a workspace card (`surface_container_lowest`) should sit on a background of `surface_container_low`. The contrast between the pure white and the soft grey creates the edge, not a stroke.

### The "Glass & Gradient" Rule
To elevate the "Cyber" feel, floating elements (modals, dropdowns, sticky headers) must use **Glassmorphism**.
*   **Formula:** `surface_container_lowest` at 70% opacity + 20px Backdrop Blur.
*   **Signature Textures:** For primary CTAs, do not use flat hex codes. Apply a subtle linear gradient from `primary` (#8127cf) to `primary_container` (#9c48ea) at a 135-degree angle. This adds a "lithographic" depth that feels premium.

---

## 3. Typography: Technical vs. Humanist
The typographic system is a juxtaposition of the futuristic and the functional.

*   **Headlines (Space Grotesk):** This is our "Tech" voice. Its quirky, geometric terminals provide the futuristic personality. Use `display-lg` and `headline-lg` with tight tracking (-2%) to create an editorial, high-fashion impact.
*   **Body & Labels (Inter):** This is our "Human" voice. Inter is used for all functional data—booking times, seat numbers, and descriptions. Its neutral stance ensures that complex workspace data remains legible and professional.

**Editorial Tip:** Always pair a large `display-sm` headline in Space Grotesk with a `label-md` in all-caps Inter (tracked out to +10%) for a sophisticated, curated look.

---

## 4. Elevation & Depth
We reject the "drop shadow" of 2010. Our depth is environmental and tonal.

### The Layering Principle
Depth is achieved by "stacking" the `surface-container` tiers. 
1.  **Level 0 (Background):** `surface` (#f8f9fb)
2.  **Level 1 (Sub-sectioning):** `surface_container_low` (#f3f4f6)
3.  **Level 2 (Interactive Cards):** `surface_container_lowest` (#ffffff)

### Ambient Shadows
When a component must "float" (e.g., a floating action button or a hovered card), use **Ambient Shadows**:
*   **Color:** Use a 6% opacity of the `primary` color (#8127cf) rather than black.
*   **Setting:** Blur: 40px, Y-Offset: 12px. This mimics light refracting through a purple-tinted lens, reinforcing the "Cyber-Light" theme.

### The "Ghost Border" Fallback
If a border is required for accessibility (e.g., input fields), use the `outline_variant` token at **15% opacity**. A 100% opaque border is a failure of the design system's airy philosophy.

---

## 5. Components

### Buttons
*   **Primary:** Gradient fill (`primary` to `primary_container`), `on_primary` text, 8px rounded corners. No border.
*   **Secondary:** `surface_container_high` background with `primary` text. Provides contrast without competing for attention.
*   **State:** On hover, increase the gradient saturation; do not use a dark overlay.

### Input Fields
*   **Styling:** Pure white background (`surface_container_lowest`) with a "Ghost Border" (15% `outline_variant`). 
*   **Focus State:** The border transitions to 100% `primary` with a 4px soft outer glow of the same color.

### Workspace Cards & Lists
*   **Strict Rule:** No dividers. Use 24px or 32px of vertical whitespace to separate items.
*   **Layout:** Use asymmetrical padding (e.g., more padding on the left than the right) to create an unconventional, high-end rhythmic flow.

### Glass Tooltips
*   Use the Glassmorphism formula (70% opacity + blur). Tooltips should feel like HUD elements floating over the interface.

### Additional Component: "The Status Pulse"
For real-time availability (e.g., "Desk 4 is free"), use a small 8px circle with a subtle `primary` glow animation. This adds "life" to the minimalist interface.

---

## 6. Do’s and Don’ts

### Do:
*   **Embrace White Space:** If you think there is enough margin, add 8px more. The system relies on "breathing room."
*   **Use Intentional Asymmetry:** Align text to the left but place supporting imagery or data visualizations slightly offset to break the "grid-lock."
*   **Layer Surfaces:** Use the `surface_container` tiers to create hierarchy.

### Don't:
*   **Don't Use Pure Black:** Use `on_surface` (#191c1e) for text. Pure black is too harsh for this "Light" system.
*   **Don't Use Dark Shadows:** Shadows should be purple-tinted and barely visible.
*   **Don't Use Default Inter for Headlines:** Space Grotesk is the brand's signature; using Inter for headlines makes the app look like a generic utility.
*   **No Hard Outlines:** Never use a 100% opaque grey border. It interrupts the "Luminous" flow of the page.