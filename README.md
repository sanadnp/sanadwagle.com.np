# Design System Document: The Curated Monolith

## 1. Overview & Creative North Star
This design system is built for the portfolio of Sanad Wagle, reimagining the traditional digital portfolio as a high-end editorial exhibition. The **Creative North Star** for this system is **"The Curated Monolith."** 

We are moving away from the "web-as-an-app" feel and toward a "web-as-a-gallery" experience. This is achieved through intentional asymmetry, extreme typographic tension, and a refusal to use traditional structural dividers. Every element should feel like it was placed by a curator—purposeful, heavy with meaning, and surrounded by "dead air" (strategic whitespace) that allows the work to breathe. We reject the "rounded-web" trend; here, sharp 0px corners convey precision, authority, and a modern architectural edge.

## 2. Colors: The Tonal Spectrum
The palette is strictly monochrome, but it is far from flat. We use Material Design tokens to create a sophisticated layering system that mimics physical light falling on premium paper and glass.

### The Palette
- **Core Surface:** `surface` (#f9f9f9) — Our crisp, gallery-wall white.
- **The Absolute:** `primary` (#000000) — Used for high-impact typography and primary actions.
- **Deep Tones:** `secondary` (#5f5e5e) and `tertiary` (#3b3b3c) — Used for secondary metadata and depth.

### The "No-Line" Rule
Standard UI relies on 1px borders to separate content. **In this design system, borders are prohibited.** Sectioning must be achieved through:
1.  **Background Color Shifts:** Transitioning from `surface` to `surface-container-low` (#f3f3f3) to define a new content area.
2.  **Vertical Whitespace:** Using the spacing scale to create rhythmic breaks.
3.  **Tonal Nesting:** Placing a `surface-container-lowest` (#ffffff) card against a `surface-container` (#eeeeee) background to create a "lifted" effect without lines.

### Glass & Texture
To prevent the monochrome look from feeling "dead," use **Glassmorphism** for floating navigation or overlays. Utilize semi-transparent `surface-variant` (#e2e2e2 at 70% opacity) with a `backdrop-filter: blur(20px)`. This creates a frosted-glass effect that integrates the foreground with the content underneath.

## 3. Typography: Editorial Tension
We employ two contrasting typefaces to create a signature "High-End Editorial" look: **Newsreader** (a sophisticated serif) for emotional impact and **Inter** (a modern sans-serif) for technical precision.

- **The Serif (Newsreader):** Used for `display` and `headline` levels. It represents the "Artist." It should be set with tight letter-spacing and used at large scales (`display-lg` at 3.5rem) to dominate the layout.
- **The Sans (Inter):** Used for `title`, `body`, and `label`. It represents the "Curator." It provides the data, the descriptions, and the navigation. 

**Typographic Hierarchy as Identity:** 
Juxtapose a massive `display-lg` serif headline against a tiny, all-caps `label-sm` in Inter. This high-contrast pairing is the visual signature of the brand.

## 4. Elevation & Depth: Tonal Layering
In a 0px roundedness system, depth is the only way to convey hierarchy. However, we avoid heavy drop shadows which can look "cheap."

- **The Layering Principle:** Stacking is done through the `surface-container` tiers. 
    - Base Level: `surface`
    - Inset Level: `surface-container-high` (#e8e8e8)
    - Raised Level: `surface-container-lowest` (#ffffff)
- **Ambient Shadows:** If a floating element (like a modal) is required, use an extra-diffused shadow: `box-shadow: 0 20px 50px rgba(0,0,0,0.04)`. The shadow must feel like ambient light, not a dark smudge.
- **The Ghost Border:** For accessibility in input fields, use a "Ghost Border"—the `outline-variant` (#c6c6c6) at 20% opacity. It should be barely visible, felt rather than seen.

## 5. Components

### Buttons
- **Primary:** Solid `primary` (#000000) with `on-primary` (#e5e2e1) text. Sharp 0px corners. High-speed hover state (0.2s transition) shifting to `primary_container` (#3c3b3b).
- **Tertiary (Ghost):** No background or border. Underlined `on-surface` text. The underline should be a 1px offset that disappears on hover.

### Cards & Gallery Items
- **Rule:** No borders, no shadows.
- **Style:** Use a `surface-container-low` (#f3f3f3) background. The image within the card should be full-bleed. On hover, the image should subtly scale (1.05x) within its sharp container to create a "premium lens" effect.

### Input Fields
- **Style:** Minimalist. Only a bottom border using `outline` (#777777). 
- **Active State:** The bottom border transforms into a 2px `primary` (#000000) line. Label (`label-md`) moves above the field in Inter.

### Lists
- **Style:** Forbid the use of divider lines. Separate items with increased padding and alternating `surface` to `surface-container-lowest` backgrounds if necessary.

### Navigation
- **Style:** A fixed "Monolith" bar at the top or bottom. Use the **Glassmorphism** rule (blurred `surface-variant`) to allow the portfolio work to scroll elegantly beneath the UI.

## 6. Do’s and Don’ts

### Do:
- **Embrace Asymmetry:** Place a `display-lg` headline on the left and a small `body-md` paragraph on the far right. Use the grid to create "tension."
- **Use "Scale" as a Feature:** Make your headlines larger than you think they should be and your labels smaller (but legible).
- **Focus on Motion:** Interactions should be "snappy yet smooth." Use `cubic-bezier(0.16, 1, 0.3, 1)` for all transitions to mimic the feel of a luxury camera shutter.

### Don’t:
- **No Rounded Corners:** Never use `border-radius`. Everything is 0px. Sharpness is our aesthetic.
- **No Pure Grey Shadows:** Never use `#000000` at 20% for shadows. Use tinted shadows or, preferably, tonal shifts.
- **No Clutter:** If a design element doesn't serve the "Digital Gallery" purpose, remove it. If the page feels empty, keep it that way—that is "Gallery Elegance."