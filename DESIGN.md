---
name: Luminous Violet Macro Tracker
colors:
  surface: '#fcf8ff'
  surface-dim: '#dad6ff'
  surface-bright: '#fcf8ff'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#f6f2ff'
  surface-container: '#efebff'
  surface-container-high: '#e9e5ff'
  surface-container-highest: '#e3dfff'
  on-surface: '#181445'
  on-surface-variant: '#4a4455'
  inverse-surface: '#2d2a5b'
  inverse-on-surface: '#f3eeff'
  outline: '#7b7486'
  outline-variant: '#ccc3d7'
  surface-tint: '#7331df'
  primary: '#5300b7'
  on-primary: '#ffffff'
  primary-container: '#6d28d9'
  on-primary-container: '#dac5ff'
  inverse-primary: '#d3bbff'
  secondary: '#6b38d4'
  on-secondary: '#ffffff'
  secondary-container: '#8455ef'
  on-secondary-container: '#fffbff'
  tertiary: '#5d3900'
  on-tertiary: '#ffffff'
  tertiary-container: '#7d4e00'
  on-tertiary-container: '#ffc47d'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#ebddff'
  primary-fixed-dim: '#d3bbff'
  on-primary-fixed: '#250059'
  on-primary-fixed-variant: '#5b00c5'
  secondary-fixed: '#e9ddff'
  secondary-fixed-dim: '#d0bcff'
  on-secondary-fixed: '#23005c'
  on-secondary-fixed-variant: '#5516be'
  tertiary-fixed: '#ffddb8'
  tertiary-fixed-dim: '#ffb95f'
  on-tertiary-fixed: '#2a1700'
  on-tertiary-fixed-variant: '#653e00'
  background: '#fcf8ff'
  on-background: '#181445'
  surface-variant: '#e3dfff'
typography:
  display-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 40px
    fontWeight: '800'
    lineHeight: 48px
    letterSpacing: -0.03em
  display-lg-mobile:
    fontFamily: Plus Jakarta Sans
    fontSize: 32px
    fontWeight: '800'
    lineHeight: 38px
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 28px
    fontWeight: '700'
    lineHeight: 34px
    letterSpacing: -0.02em
  headline-md:
    fontFamily: Plus Jakarta Sans
    fontSize: 22px
    fontWeight: '700'
    lineHeight: 28px
    letterSpacing: -0.015em
  headline-sm:
    fontFamily: Plus Jakarta Sans
    fontSize: 18px
    fontWeight: '600'
    lineHeight: 24px
    letterSpacing: -0.01em
  body-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
  body-md:
    fontFamily: Plus Jakarta Sans
    fontSize: 14px
    fontWeight: '400'
    lineHeight: 20px
  body-sm:
    fontFamily: Plus Jakarta Sans
    fontSize: 12px
    fontWeight: '400'
    lineHeight: 16px
  label-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 14px
    fontWeight: '600'
    lineHeight: 18px
    letterSpacing: 0.01em
  label-md:
    fontFamily: Plus Jakarta Sans
    fontSize: 12px
    fontWeight: '600'
    lineHeight: 16px
    letterSpacing: 0.02em
  label-sm:
    fontFamily: Plus Jakarta Sans
    fontSize: 10px
    fontWeight: '700'
    lineHeight: 14px
    letterSpacing: 0.04em
  numeric-stat:
    fontFamily: Plus Jakarta Sans
    fontSize: 24px
    fontWeight: '800'
    lineHeight: 28px
    letterSpacing: -0.02em
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  gutter: 1rem
  gutter-sm: 0.75rem
  margin: 1.25rem
  margin-tablet: 2rem
  margin-desktop: 3rem
  space-xs: 0.25rem
  space-sm: 0.5rem
  space-md: 1rem
  space-lg: 1.5rem
  space-xl: 2rem
  space-2xl: 3rem
---

## Brand & Style

The design system establishes a high-precision, premium health-and-nutrition experience. It steers away from the clinical, sterile green aesthetic traditionally found in diet applications, embracing instead an empowering, focused, and sophisticated aura driven by deep violets and luminous lavenders.

### Personality & Tone
- **Precision & Clarity:** Data-dense nutritional metrics (grams, percentages, calories) are displayed with effortless hierarchy and immediate readability.
- **Empowering & Non-Judgmental:** Encouraging visual cues, smooth progress arcs, and soft feedback states that inspire consistent daily logging rather than guilt.
- **Modern Tactility:** Polished surfaces, subtle frosted glass layers, and pill-shaped metrics that invite continuous micro-interactions throughout the user's day.

### Visual Style
A refined synthesis of **Modern Minimalist Utility** and **Luminous Glassmorphism**. Clean, elevated cards sit above a crisp, off-white background with whisper-quiet violet ambient shadows. Micro-surfaces use subtle radial gradients and translucent borders to evoke depth without visual friction or cognitive fatigue.

## Colors

The palette revolves around deep ultraviolet, vibrant orchid tones, and clear semantic contrasts tailored specifically for macronutrient breakdown:

- **Primary (`#6D28D9` - Deep Violet):** Anchor color for top-level navigation, primary call-to-actions, and Protein macro indicators.
- **Secondary (`#8B5CF6` - Vibrant Purple):** Active toggle states, key progress highlights, and Carbohydrate macro indicators.
- **Tertiary (`#F59E0B` - Warm Amber Gold):** Dedicated contrast accent specifically reserved for Fat intake tracking and achievement/streak callouts.
- **Neutral Primary (`#1E1B4B` - Midnight Indigo):** Grounding dark slate for high-contrast headlines and critical numeric data.
- **Canvas Base (`#FAFAFC`):** Crisp, ultra-clean off-white background designed to optimize battery efficiency and reduce eye strain in daylight logging.
- **Tonal Tints:** 
  - Soft Lavender (`#EDE9FE`) for component backgrounds, inactive track indicators, and tag containers.
  - Success Mint (`#10B981`) for hitting caloric goals without exceeding limits.
  - Alert Rose (`#F43F5E`) for over-target warnings.

## Typography

Plus Jakarta Sans provides geometric balance with contemporary rounded terminals, matching the approachable yet disciplined nature of nutritional tracking.

### Rules & Formatting
- **Tabular Figures:** Always apply `font-feature-settings: "tnum" 1` to numeric counters, macro inputs, and calorie ring summaries to eliminate jitter during value updates.
- **Macro Micro-Labels:** `label-sm` is rendered in uppercase with positive letter spacing (`0.04em`) when positioning macro abbreviations (e.g., `PRO`, `CARB`, `FAT`) alongside progress bars.
- **Hierarchy Stacking:** Pair large bold numeric readouts (`numeric-stat`) directly over muted descriptor labels (`label-md`) with minimal vertical spacing (`space-xs`) to maintain cohesion.

## Layout & Spacing

The system implements a fluid, column-disciplined grid optimized for vertical scroll dynamics on mobile handheld devices.

### Layout Mechanics
- **Mobile Grid (up to 599px):** 4-column layout with `margin: 1.25rem` and `gutter: 0.75rem`. Cards generally span all 4 columns, or split into 2-column cards for side-by-side macro indicators.
- **Tablet Grid (600px - 1023px):** 8-column layout with `margin-tablet: 2rem` and `gutter: 1rem`. Nutritional overview sits on a 5-column primary stack, paired with a 3-column meal log side-rail.
- **Desktop Grid (1024px+):** 12-column layout centered at a max width of `1200px` with `margin-desktop: 3rem`. Daily macro rings dock permanently on the left (4 columns) while meal logging timelines expand into the right canvas (8 columns).
- **Rhythm Principle:** Internal card padding is uniformly set to `space-lg` (`1.5rem`) for high-level summaries and `space-md` (`1rem`) for dense meal item rows.

## Elevation & Depth

Depth is established through soft, violet-tinted atmospheric shadows and low-contrast borders rather than harsh drop shadows.

### Elevation Hierarchy
1. **Level 0 (Flat Ground):** Background `#FAFAFC` without borders or shadows.
2. **Level 1 (Summary & Meal Cards):** Background `#FFFFFF`, border `1px solid rgba(109, 40, 217, 0.06)`, shadow `0 4px 20px -2px rgba(30, 27, 75, 0.04)`.
3. **Level 2 (Active States & Popovers):** Background `#FFFFFF`, border `1px solid rgba(139, 92, 246, 0.16)`, shadow `0 10px 25px -4px rgba(109, 40, 217, 0.08)`.
4. **Level 3 (Sticky Bottom Bar & Modals):** Frosted glass effect (`rgba(255, 255, 255, 0.85)` with `backdrop-filter: blur(16px)`), top border `1px solid rgba(109, 40, 217, 0.12)`, shadow `0 -6px 24px -2px rgba(30, 27, 75, 0.06)`.

## Shapes

The interface utilizes a friendly, organic rounded language (`roundedness: 2`) that softens quantitative data without appearing childish.

### Corner Radius Mapping
- **Default Elements (`0.5rem` / `8px`):** Checkboxes, form fields, chips, small macro badges.
- **Large Containers (`1rem` / `16px`):** Standard daily meal cards, macro breakdown sections, quick-log input cards.
- **Extra Large Containers (`1.5rem` / `24px`):** Hero calorie summary dashboards, bottom sheets, full modal surfaces.
- **Full Pill (`9999px`):** Primary action buttons, segmented meal toggles (Breakfast, Lunch, Dinner, Snack), and dynamic progress track caps.

## Components

### Buttons
- **Primary Action:** Full pill button with background `#6D28D9`, text `#FFFFFF`, font `label-lg`. On hover/tap, transitions smoothly to `#5B21B6` with an inner glow `inset 0 1px 0 rgba(255, 255, 255, 0.2)`.
- **Secondary Action:** Pill button with background `#EDE9FE`, text `#6D28D9`, and no border. Active state applies background `#DDD6FE`.
- **Quick-Add Floating Action Button (FAB):** Circular (`56px x 56px`), `#6D28D9` fill, centered white plus icon, elevated with Level 2 shadow.

### Circular Progress Rings (Macro & Calorie Rings)
- **Geometry:** Triple-nested or multi-segment SVG rings with rounded stroke caps (`stroke-linecap: round`).
- **Background Track:** Light tinted stroke using `#EDE9FE` at `8px` width.
- **Active Segments:** 
  - Protein: `#6D28D9`
  - Carbohydrates: `#8B5CF6`
  - Fats: `#F59E0B`
- **Center Content:** Calorie balance remaining rendered in `numeric-stat` over `label-sm` ("KCAL LEFT").

### Meal & Nutrition Cards
- **Structure:** Surface white `#FFFFFF` with `rounded-xl` corners and Level 1 elevation.
- **Header:** Meal title in `headline-sm`, subtitle showing total calories right-aligned in `label-lg`.
- **Linear Macro Bars:** Slim (`6px` height) pill tracks below meal items, visually partitioning the three macro components proportionally.

### Chips & Tags
- **Meal Category Chips:** Segmented pill filters with a base state of transparent background and `1px solid #E2E8F0`. When selected, fills with `#EDE9FE`, text `#6D28D9`, and border `#C4B5FD`.

### Input Fields & Calorie Calculator Sliders
- **Numeric Macro Inputs:** Generous height (`48px`), `rounded-md`, background `#FFFFFF`, border `1.5px solid #E2E8F0`. Focus state shifts border to `#6D28D9` with `0 0 0 3px rgba(109, 40, 217, 0.12)`.
- **Target Adjuster Sliders:** Custom thumb using a solid `#6D28D9` circle with a `#FFFFFF` outer ring, moving across an `#EDE9FE` track filled dynamically up to the thumb position.

### Checkboxes & Micro-Interactions
- **Checkbox:** `20px x 20px`, `rounded-sm` (`4px`). Unchecked has a clean slate border `#CBD5E1`. Checked triggers a vibrant `#6D28D9` fill with a crisp white checkmark SVG and gentle spring animation.