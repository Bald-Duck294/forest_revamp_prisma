# Design System Specification: The Ethereal Utility

## 1. Overview & Creative North Star
**Creative North Star: "The Grounded Precision"**

This design system moves away from the clinical, "boxed-in" nature of standard utility software. For a company operating at the intersection of forestry, water management, and infrastructure in Maharashtra, the UI must feel as reliable as a boom barrier and as fluid as the Jaltara water systems. 

We achieve "The Grounded Precision" by rejecting the rigid 1px border. Instead, we use **Tonal Architecture**—a method of defining space through subtle shifts in surface color and "weighted" typography. The layout should feel editorial and expansive, using intentional asymmetry to guide the eye through complex environmental data. We are not just building a dashboard; we are creating a digital reflection of managed nature.

---

## 2. Colors & Surface Philosophy
The palette is rooted in the deep greens of Maharashtra’s forest cover (`primary`) and the professional blues of water conservation (`secondary`).

### The "No-Line" Rule
**Explicit Instruction:** 1px solid borders for sectioning are strictly prohibited. 
Boundaries must be defined solely through background color shifts. For instance, a `surface-container-low` section should sit directly against a `surface` background to create a "soft edge." This mimics the natural transitions found in landscapes.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—stacked sheets of heavy-weight paper or frosted glass.
- **Base Layer:** `surface` (#f8fafb)
- **Primary Content Areas:** `surface-container-low` (#f2f4f5)
- **Interactive Cards:** `surface-container-lowest` (#ffffff)
- **High-Priority Modals:** `surface-container-highest` (#e1e3e4)

### The "Glass & Gradient" Rule
To elevate the experience, use **Backdrop Blurs** (20px - 40px) on floating navigation bars using `surface` at 80% opacity. 
- **Signature Texture:** For Hero sections or primary CTAs, apply a linear gradient from `primary` (#00450d) to `primary-container` (#1b5e20) at a 135-degree angle. This adds "soul" and depth that flat hex codes lack.

---

## 3. Typography: The Editorial Authority
We utilize a dual-font strategy to balance bold presence with high-utility readability.

*   **Display & Headlines (Manrope):** Chosen for its geometric precision and modern "tech-meets-nature" feel. 
    *   `display-lg` (3.5rem): Use for high-impact forestry stats or hero statements.
    *   `headline-md` (1.75rem): Bold, authoritative headers for service categories (e.g., "Water Management").
*   **Body & Labels (Inter):** The industry standard for legibility.
    *   `body-lg` (1rem): Used for all primary descriptions and reports.
    *   `label-md` (0.75rem): All-caps with 0.05em letter spacing for metadata (e.g., TOILET RATING).

**Hierarchy Rule:** Never center-align long-form text. Maintain a strict left-aligned "axis" to create a professional, stable reading experience.

---

## 4. Elevation & Depth
Depth is achieved through **Tonal Layering**, not structural lines.

*   **The Layering Principle:** Place a `surface-container-lowest` card on a `surface-container-low` section. The change from #f2f4f5 to #ffffff provides a sophisticated "lift" without visual clutter.
*   **Ambient Shadows:** If a floating element (like a FAB or Popover) requires a shadow, use: 
    *   `box-shadow: 0 20px 40px rgba(25, 28, 29, 0.06);` 
    *   The shadow color must be a tinted version of `on-surface` (#191c1d) to mimic natural light.
*   **The Ghost Border Fallback:** If accessibility requires a border (e.g., in high-contrast modes), use `outline-variant` (#c0c9bb) at **15% opacity**.

---

## 5. Components

### Buttons
*   **Primary:** Solid `primary` (#00450d) with `on-primary` text. Use `xl` (0.75rem) roundedness.
*   **Secondary:** `secondary-container` (#62b4fe) with `on-secondary-container` text. No border.
*   **Tertiary:** Transparent background with `primary` text. Use only for low-priority actions like "Cancel" or "View Less."

### Cards & Lists
*   **Rule:** Forbid divider lines. 
*   **Implementation:** Use the Spacing Scale `8` (2rem) to separate list items. Use a `surface-container-low` background on hover to indicate interactivity. 
*   **Service Cards:** Use `surface-container-lowest` with a 2px "Top Accent" of `primary` or `secondary` to categorize forestry vs. water management.

### Input Fields
*   **Surface:** `surface-container-highest` with a bottom-only "active" bar of `primary` (2px).
*   **States:** On `error`, the background shifts to `error-container` (#ffdad6) with `on-error-container` text.

### Specialized Components
*   **Rating Chips (Sanitation):** For toilet ratings, use a pill-shaped chip (`full` roundedness) using `tertiary-container` for the background and `on-tertiary-container` for the text.
*   **Status Indicators (Boom Barriers):** Use `primary-fixed` for "Active/Open" and `error` for "Closed/Alert," but always accompany the color with a `label-sm` text tag for accessibility.

---

## 6. Do’s and Don’ts

### Do
*   **Do** use asymmetrical whitespace. A larger left margin than right margin creates a sophisticated, editorial feel.
*   **Do** use `primary-fixed-dim` (#91d78a) for subtle highlights in dark-themed components.
*   **Do** ensure all "Water" related UI elements use the `secondary` (#00629e) blue to maintain mental models.

### Don’t
*   **Don’t** use pure black (#000000) for text. Always use `on-background` (#191c1d) to maintain a premium, softer look.
*   **Don’t** use the `DEFAULT` (0.25rem) roundedness for large containers; it looks dated. Use `xl` (0.75rem) for cards and `lg` (0.5rem) for buttons.
*   **Don’t** use "Drop Shadows" on standard cards. Let the background color shifts do the heavy lifting.