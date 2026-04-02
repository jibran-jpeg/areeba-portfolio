# Design System Strategy: The Digital Curator

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Digital Curator."** 

Unlike standard portfolios that rely on rigid, clinical grids, this system embraces the tactile warmth of a physical scrapbook. It is designed to feel "hand-assembled"—intentional, layered, and deeply personal. We move beyond the "AI-slop" aesthetic by prioritizing human-centric imperfections: subtle rotations, overlapping paper textures, and "taped-on" elements. 

The layout logic breaks the template feel through **intentional asymmetry**. While a functional underlying grid exists, components should "float" or overlap across column boundaries to mimic a desk covered in sketches and clippings. This approach balances the organization of a professional graphic designer with the whimsical soul of an illustrator.

## 2. Colors
Our palette balances soft, pastel nostalgia with high-contrast functional accents to ensure the "scrapbook" remains highly readable and accessible.

*   **Primary Logic:** We use `primary` (#3f57a4) for authoritative actions and `primary_container` (#93aafe) for broader periwinkle washes.
*   **Secondary & Tertiary Accents:** Use `secondary` (ochre/yellow) and `tertiary` (dusty pink/red) for "highlighted" elements—like paper-clips, hand-drawn stars, or "must-see" labels.
*   **The "No-Line" Rule:** Explicitly prohibit 1px solid borders for sectioning. Structural boundaries must be defined solely through background shifts. For example, a project gallery section using `surface_container_low` should sit directly on the `background` (#f1f8fa) without a dividing line.
*   **Surface Hierarchy & Nesting:** Treat the UI as physical layers.
    *   **Base:** `background`
    *   **The "Paper" Sheet:** `surface_container_lowest` (#ffffff) for high-focus content.
    *   **The "Pinned" Note:** `surface_container_high` (#dae4e7) for secondary callouts.
*   **The "Glass & Gradient" Rule:** Floating navigation bars or "quick-view" overlays should utilize Glassmorphism (semi-transparent `surface` tokens with a 12px backdrop-blur) to soften edges. Use subtle gradients from `primary` to `primary_container` for primary CTAs to inject "visual soul" and depth.

## 3. Typography
The typography system is a conversation between the hand-drawn (Epilogue) and the architectural (Manrope).

*   **Display & Headlines (Epilogue):** Used for big, quirky statements. The `display-lg` (3.5rem) and `headline` tiers represent the "marker-drawn" titles of a scrapbook. They should feel bold, playful, and expressive.
*   **Body & Titles (Manrope):** This is the functional backbone. Use `body-lg` for project descriptions to maintain high legibility. 
*   **Labels (Manrope):** Small-caps or tight tracking on `label-md` should be used for technical details (e.g., "Software: Adobe Illustrator") to provide a professional counterweight to the playful headers.

## 4. Elevation & Depth
Depth is the most critical factor in achieving the "tactile" feel. We reject standard Material Design shadows in favor of "Tonal Layering."

*   **The Layering Principle:** Stack `surface-container` tiers to create lift. A `surface_container_lowest` card placed on a `surface_dim` background creates a natural, soft separation.
*   **Ambient Shadows:** When a card must "float" (like a taped-down photo), use an extra-diffused shadow.
    *   **Token:** Use `on_surface` color at 6% opacity.
    *   **Settings:** Blur: 24px, Spread: -2px, Offset-Y: 8px. This mimics soft desk lighting.
*   **The "Ghost Border" Fallback:** If a border is required for accessibility, use the `outline_variant` token at **15% opacity**. Never use 100% opaque borders.
*   **Tactile Accents:** Use the `roundedness` scale `lg` (1rem) for most cards to mimic die-cut paper. Use `full` (9999px) for "pill" buttons that feel like stickers.

## 5. Components

### Buttons
*   **Primary:** Pill-shaped (`rounded-full`), using a `primary` background. Hover states should "lift" slightly with an `Ambient Shadow`.
*   **Secondary:** Styled as a "taped-on" label using `secondary_container` with a slight 1-2 degree rotation.

### Cards & Lists
*   **Forbid divider lines.** Separate list items using `surface_container_low` backgrounds or generous vertical whitespace (Spacing Scale `6` or `8`).
*   **Scrapbook Cards:** Every card must feel like a separate piece of paper. Use `surface_container_lowest` with a subtle `outline_variant` "Ghost Border" and varied `roundedness-md` to `lg`.

### Hand-Drawn Elements (Custom Primitives)
*   **Washi Tape:** A decorative container for titles using `secondary_container` or `tertiary_container` with jagged, masked edges.
*   **Stamps/Badges:** Use `tertiary` for small circular "Illustration" badges, placed at overlapping corners of images.

### Input Fields
*   **Text Inputs:** Minimalist `surface_variant` backgrounds. Focus states should not use a glow but rather a bold `primary` underline (2px) to mimic a pen-drawn line.

## 6. Do's and Don'ts

### Do:
*   **Embrace Rotation:** Slightly rotate elements (±1-3 degrees) like photos or sticky notes to break the digital rigidity.
*   **Overlap Content:** Allow an illustration or a "tape" texture to overlap two containers, binding them together visually.
*   **Use Grid Patterns:** Apply a subtle dot-grid or graph-paper pattern to the `surface_container_low` background to reinforce the "designer's sketchbook" theme.

### Don't:
*   **Don't use pure black:** Use `on_background` (#293032) for all text to keep the aesthetic soft and high-end.
*   **Don't align everything perfectly:** If every card edge perfectly aligns, the "scrapbook" soul is lost. Use the Spacing Scale to create intentional offsets.
*   **Avoid standard "Drop Shadows":** Never use high-opacity, tight-radius shadows. They feel "corporate" and break the soft, editorial tone.