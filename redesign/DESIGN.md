# Design System: The Sovereign Counsel

## 1. Overview & Creative North Star: "The Silent Authority"
In high-complexity criminal law, the digital experience must mirror the gravitas of a closed-door legal chamber. This design system departs from generic "corporate blue" templates, adopting a **Creative North Star of "The Silent Authority."** 

The interface is designed to feel like a high-end editorial publication—confidential, serious, and immovable. We achieve this by breaking the rigid, boxed-in grids of standard web design. Instead, we use **intentional asymmetry**, where content breathes within expansive whitespace, and **layered depth**, where information is revealed through frosted glass surfaces rather than harsh partitions. It is a system of "Quiet Luxury": it doesn't shout for attention; it commands it through precision and restraint.

---

### 2. Colors: Tonal Depth & The Gold Standard
The palette is rooted in deep judicial tones, punctuated by rich bronze and gold accents that signify heritage and excellence.

*   **Primary (#785916) & Tertiary (#745B00):** These are your "Gold/Bronze" tokens. Use them sparingly for critical emphasis and interactive "glows."
*   **Surface Hierarchy:** Our "Deep Black" and "Crisp White" feel is achieved through the `surface` tokens.
*   **The "No-Line" Rule:** Explicitly prohibit the use of 1px solid borders to section off the UI. Boundaries must be defined solely through background color shifts. For example, a `surface-container-low` section sitting on a `surface` background creates a sophisticated, invisible boundary.
*   **Surface & Nesting:** Treat the UI as physical layers. Use `surface-container-lowest` for the base layer, and `surface-container-high` for nested modules. This "paper-on-stone" stacking creates depth without clutter.
*   **The "Glass & Gradient" Rule:** Floating modals or navigation bars must utilize Glassmorphism. Use semi-transparent variants of `surface` with a `backdrop-filter: blur(20px)`.
*   **Signature Textures:** For Hero sections or primary CTAs, use a subtle linear gradient from `primary` (#785916) to `primary_container` (#D4AC61) at a 135-degree angle to provide a metallic, light-catching sheen.

---

### 3. Typography: The Editorial Voice
We contrast the classical authority of a serif with the clinical precision of a modern sans-serif.

*   **Display & Headlines (Crimson Pro / Newsreader):** Used for large statements and section titles. These should feel like a masthead. The serif nature conveys history, law, and truth.
*   **Body & Labels (DM Sans / Manrope):** Used for all functional data. The high readability of the sans-serif ensures that even the most complex legal jargon is legible and modern.
*   **Hierarchy as Narrative:** Use extreme scale contrast. A `display-lg` headline paired with a significantly smaller `body-md` creates an editorial "white space" effect that feels premium and curated.

---

### 4. Elevation & Depth: Tonal Layering
Traditional drop shadows are too "digital." We use **Ambient Light Layering** to define space.

*   **The Layering Principle:** Depth is achieved by "stacking" the `surface-container` tiers. Place a `surface-container-lowest` card on a `surface-container-low` section to create a soft, natural lift.
*   **Ambient Shadows:** If a floating effect is required (e.g., a critical legal alert), use an extra-diffused shadow: `box-shadow: 0 20px 40px rgba(0, 0, 0, 0.06)`. The shadow color must be a tinted version of the `on-surface` color, never a generic grey.
*   **The "Ghost Border" Fallback:** If a border is required for accessibility, use the `outline-variant` token at 15% opacity. High-contrast, 100% opaque borders are strictly forbidden.
*   **Interactive Glow:** On hover, primary elements should emit a subtle `primary` (#785916) outer glow (blur: 15px, spread: -5px) to simulate light reflecting off polished gold.

---

### 5. Components: Precision & Restraint

*   **Buttons:**
    *   *Primary:* Solid `primary` with `on_primary` text. No borders. Corner radius: `md` (0.375rem).
    *   *Secondary:* `surface-container-high` background with a "Ghost Border" (10% `outline-variant`).
*   **Input Fields:** Use a "Minimalist Ledger" style. Only a bottom stroke using `outline-variant` (20% opacity). When focused, the stroke transitions to `primary` with a subtle glass blur background.
*   **Cards:** Never use borders or heavy shadows. Use a subtle background shift (e.g., `surface-container-lowest`) and generous padding (`spacing-8`). 
*   **Lists:** Forbid divider lines. Use vertical white space (`spacing-4`) and `surface-variant` hover states to separate case files or legal documents.
*   **Glass Overlays:** For high-security prompts (e.g., password entry), use a full-screen `surface` overlay at 80% opacity with a heavy blur to maintain confidentiality of the background data.

---

### 6. Do’s and Don’ts

#### **Do:**
*   **Use Asymmetry:** Align text to the left but allow imagery or accents to bleed off the right edge of the grid.
*   **Prioritize Legibility:** Ensure high contrast between `on_surface` and `surface` for all legal fine print.
*   **Embrace "The Void":** Use large amounts of whitespace (`spacing-20` or `spacing-24`) between major sections to let the brand "breathe."

#### **Don’t:**
*   **No Standard Grids:** Avoid the "3-column card row" look. Offset the cards or vary their widths to feel like a custom-designed layout.
*   **No Sharp Primary Colors:** Never use pure #FF0000 for errors; use our curated `error` (#BA1A1A) to maintain the sophisticated palette.
*   **No "Heavy" Shadows:** If you can clearly see where a shadow ends, it is too dark. It should feel like a natural gradient of light.