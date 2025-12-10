# Design Specifications - Sedaghat Art Center

Complete visual design system including colors, typography, layouts, and UI components.

## 🎨 Design Philosophy

The website design reflects the artistic nature of the Sedaghat Art Center while maintaining professional elegance and accessibility.

---

## 🌈 Color Palette

### Primary Colors

**Deep Charcoal** (Main text, headers)
- Hex: `#2C2C2C`
- Usage: Body text, primary headings, navigation

**Warm Cream** (Background)
- Hex: `#FAF7F2`
- Usage: Main background, card backgrounds

**Rich Burgundy** (Primary accent)
- Hex: `#8B1E3F`
- Usage: Buttons, links, highlights, calls-to-action

### Secondary Colors

**Soft Gold** (Accent)
- Hex: `#D4AF37`
- Usage: Icons, decorative elements, hover states

**Sage Green** (Secondary accent)
- Hex: `#8A9A5B`
- Usage: Success messages, secondary buttons

**Dusty Rose** (Tertiary accent)
- Hex: `#C49792`
- Usage: Subtle highlights, Persian page elements

### Neutral Colors

**Pure White**: `#FFFFFF`
**Light Gray** (Borders): `#E5E5E5`
**Medium Gray** (Secondary text): `#6B6B6B`
**Dark Slate** (Footer): `#3A3A3A`

---

## ✏️ Typography

### Font Families

**Primary Font: Playfair Display** (Serif)
- Purpose: Headings, hero text, elegant display
- Weights: 400 (Regular), 600 (SemiBold), 700 (Bold)
- Google Fonts: `Playfair Display`

**Secondary Font: Lato** (Sans-serif)
- Purpose: Body text, navigation, UI elements
- Weights: 300 (Light), 400 (Regular), 700 (Bold)
- Google Fonts: `Lato`

**Persian Font: Vazirmatn** (Sans-serif)
- Purpose: All Persian text
- Weights: 400 (Regular), 500 (Medium), 700 (Bold)
- Google Fonts: `Vazirmatn`

### Type Scale

**Hero Title (H1)**
- Font: Playfair Display Bold
- Size: 64px desktop / 40px mobile
- Line Height: 1.2
- Color: Deep Charcoal (#2C2C2C)

**Page Title (H1)**
- Font: Playfair Display SemiBold
- Size: 48px desktop / 32px mobile
- Line Height: 1.3

**Section Heading (H2)**
- Font: Playfair Display SemiBold
- Size: 36px desktop / 28px mobile
- Line Height: 1.4

**Body Text**
- Font: Lato Regular
- Size: 16px desktop / 15px mobile
- Line Height: 1.7
- Max Width: 720px (for readability)

---

## 📐 Layout & Grid

### Container Widths

**Max Content Width**: 1400px
**Standard Content Width**: 1200px
**Narrow Content Width**: 960px

### Breakpoints
- Desktop: 1200px+
- Laptop: 992px - 1199px
- Tablet: 768px - 991px
- Mobile: < 768px

### Spacing Scale (8px baseline)
- XS: 8px
- SM: 16px
- MD: 24px
- LG: 32px
- XL: 48px
- XXL: 64px

---

## 🧩 UI Components

### Buttons

**Primary Button**
- Background: Rich Burgundy (#8B1E3F)
- Text: White
- Padding: 16px 32px
- Border Radius: 4px
- Font: Lato Bold, 16px, Uppercase
- Hover: Darken 10%, Scale 1.02

**Secondary Button**
- Background: Transparent
- Border: 2px solid Rich Burgundy
- Text: Rich Burgundy
- Hover: Background Rich Burgundy, Text White

### Forms

**Input Fields**
- Height: 48px
- Padding: 12px 16px
- Border: 1px solid Light Gray (#E5E5E5)
- Border Radius: 4px
- Font: Lato Regular, 16px
- Focus: Border Rich Burgundy

### Cards

**Standard Card**
- Background: White
- Border: 1px solid Light Gray
- Border Radius: 8px
- Padding: 24px
- Shadow: 0 2px 8px rgba(0,0,0,0.08)
- Hover: Shadow 0 4px 16px rgba(0,0,0,0.12)

---

## 📱 Responsive Behavior

### Mobile (< 768px)
- Single column layouts
- Stack all sections
- Hamburger menu
- Larger tap targets (48px minimum)

### Tablet (768px - 1199px)
- Reduced columns (2-3)
- Slightly smaller typography
- Condensed navigation

### Desktop (1200px+)
- Multi-column layouts
- Large imagery
- Full navigation visible

---

## 🌐 Bilingual Design Considerations

### English (LTR)
- Left-aligned text
- Navigation left-to-right

### Persian (RTL)
- Right-aligned text
- Navigation right-to-left
- Font: Vazirmatn
- Line-height: 1.8 (slightly taller)
- Font Size: 17px (slightly larger)

---

## 🎨 Visual Elements

### Decorative Patterns
- Persian geometric patterns (subtle)
- Opacity: 5-10%
- Color: Soft Gold or Sage Green

### Iconography
- Style: Line icons (2px stroke)
- Size: 24px standard
- Color: Deep Charcoal

### Shadows
- Card: `0 2px 8px rgba(0,0,0,0.08)`
- Hover: `0 4px 16px rgba(0,0,0,0.12)`
- Modal: `0 8px 32px rgba(0,0,0,0.16)`

---

## 🎬 Animations & Transitions

### General Principles
- Subtle and purposeful
- Duration: 0.3s for most transitions
- Easing: ease-in-out

### Common Animations
- Fade In: Opacity 0 → 1 (0.5s)
- Slide Up: translateY(20px) → 0 (0.6s)
- Scale on Hover: scale(1) → scale(1.02) (0.3s)

---

## 📸 Photography Guidelines

### Artwork Photography
- High resolution (min 2000px wide)
- Accurate color representation
- Neutral background
- Consistent lighting

### Portrait Photography
- Professional headshots
- Natural lighting
- High resolution

---

**Last Updated**: December 9, 2024
**Document Version**: 1.0
