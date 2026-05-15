# Minecraft Bingo - Design Guide

This document provides design guidelines for the Minecraft-themed social bingo game. All UI components should follow the Minecraft aesthetic established in this guide.

## Visual Theme

The app uses a **blocky, pixelated Minecraft aesthetic** across all screens.

### Design Principles
- **Blocky & Pixelated**: Use 3px borders, no rounded corners, sharp angles
- **Authentic Minecraft**: Mimic the blocky world of Minecraft with visual depth using inset shadows
- **Pixel Font**: Use `Roboto Mono` monospace font for that retro video game feel
- **Color-Coded Blocks**: Different block types represent game states (stone for unmarked, grass for marked, ore for special)

---

## Color Palette

All colors are inspired by Minecraft's block textures:

| Block Type | Use Case | Color | Hex |
|-----------|----------|-------|-----|
| **Dirt** | Background, text | Warm brown | `#8B7355` |
| **Grass** | Primary action (buttons, marked squares) | Grass green | `#7CB342` |
| **Stone** | Game board squares (unmarked) | Gray stone | `#7F8B8B` |
| **Gold Ore** | Highlights, victory, free space | Bright gold | `#FFB90F` / `#FFD700` |
| **Oak Wood** | Header, decorative panels | Wood brown | `#8B6914` |
| **Dark Stone** | Borders, shadows | Very dark | `#3C2415` |
| **Sky Blue** | Background gradient (top) | Sky blue | `#87CEEB` |
| **Sky Gradient** | Background gradient (bottom) | Light cyan | `#E0F6FF` |

### CSS Utility Classes
```css
.bg-grass           /* Primary: #7CB342 */
.bg-stone           /* Board squares: #7F8B8B */
.bg-ore             /* Highlights: #FFB90F */
.bg-dirt            /* Background: #8B7355 */
.bg-wood            /* Headers: #8B6914 */
.text-amber-900     /* Text on grass blocks */
.text-white         /* Text on stone blocks */
```

---

## Component Styling

### Buttons
- **Border**: 3px solid with block color
- **Background**: Linear gradient with inset shadows for 3D effect
- **Hover**: Translate up 2px, add drop shadow
- **Active**: Inset shadow, translate down 2px
- **Font**: Bold, uppercase, monospace

Example:
```html
<button class="bg-grass text-white font-bold py-4 px-8" 
        style="border: 3px solid #558B2F; text-transform: uppercase;">
  ⛏️ START MINING
</button>
```

### Game Board Squares
- **Base**: Stone block (`bg-stone` / `#7F8B8B`)
- **Border**: 3px solid dark stone (`#3C2415`)
- **Marked**: Grass green (`bg-grass`)
- **Winning**: Gold ore (`bg-ore`) with glow animation
- **Free Space**: Gold ore, always disabled, bold text

Marked squares have a subtle glowing animation:
```css
@keyframes markedGlow {
    0%, 100% { box-shadow: inset 0 0 0 rgba(124, 179, 66, 0.5); }
    50% { box-shadow: inset 0 0 12px rgba(124, 179, 66, 0.8); }
}
```

### Header (Mining HUD)
- **Background**: Wood gradient (`#8B6914` → `#6B5310`)
- **Border**: 4px solid dark stone (`#3C2415`)
- **Box Shadow**: `0 4px 0 rgba(0, 0, 0, 0.3)` for depth
- **Text**: Amber brown, bold, uppercase

### Victory Modal
- **Background**: Gold gradient (`#FFD700` → `#FFA500`)
- **Border**: 6px solid dark gold (`#CD8500`)
- **Box Shadow**: Inset shadow + drop shadow for dimension
- **Title**: "VICTORY!" in large pixelated text with text-shadow
- **Emojis**: `⭐ 💎 ⭐` for celebration

### Crafting Panel (Start Screen)
- **Background**: Wood gradient similar to header
- **Border**: 4px solid with inset highlight
- **Box Shadow**: Inset colored shadow + drop shadow
- **Pattern**: Grid overlay using CSS background-image
- **Text**: Amber brown, bold

Example styling:
```css
.crafting-panel {
    background: linear-gradient(135deg, #8B6914 0%, #6B5310 100%);
    border: 4px solid #3C2415;
    box-shadow: inset 0 0 0 2px #CD8500, 0 8px 0 rgba(0, 0, 0, 0.5);
}

.crafting-panel::before {
    background-image: 
        linear-gradient(90deg, rgba(0,0,0,0.1) 1px, transparent 1px),
        linear-gradient(rgba(0,0,0,0.1) 1px, transparent 1px);
    background-size: 20px 20px;
}
```

---

## Typography

### Font Stack
```css
font-family: 'Roboto Mono', monospace;
```

### Text Sizes
- **Title**: `text-5xl` (3rem) with `pixel-text` shadow
- **Subtitle**: `text-lg` (1.125rem), uppercase
- **Section Headers**: `text-lg` with uppercase styling
- **Body Text**: `text-sm` (0.875rem)
- **Metadata**: `text-xs` (0.75rem)

### Text Effects
- **Pixel Text Shadow**: `text-shadow: 2px 2px 0 rgba(0, 0, 0, 0.5), 4px 4px 0 rgba(0, 0, 0, 0.3);`
- **Text Styling**: Uppercase letters, increased letter-spacing (1-2px)
- **Emphasis**: Bold weight, darker colors

---

## Animations

### Block Placement
When a square is marked or a new element appears:
```css
@keyframes blockPlace {
    0% { transform: scale(0.5); opacity: 0; }
    50% { transform: scale(1.1); }
    100% { transform: scale(1); opacity: 1; }
}

.animate-place {
    animation: blockPlace 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
}
```

### Marked Square Glow
Subtle infinite animation for marked squares:
```css
@keyframes markedGlow {
    0%, 100% { box-shadow: inset 0 0 0 rgba(124, 179, 66, 0.5); }
    50% { box-shadow: inset 0 0 12px rgba(124, 179, 66, 0.8); }
}

.marked-square {
    animation: markedGlow 1.5s ease-in-out infinite;
}
```

### Button Interactions
- **Hover**: 2px upward translate + drop shadow
- **Active**: 2px downward translate + inset shadow
- **Duration**: 100ms for snappy feel

---

## Screen Layouts

### Home Screen
- **Background**: Sky gradient (blue → cyan)
- **Container**: Centered column, max-width 24rem
- **Header**: Large "⛏️ MINECRAFT BINGO" title with pixel-text shadow
- **Subheader**: "🎮 Social Mining Challenge" in brown
- **Panel**: Crafting table aesthetic with "How to Mine" instructions
- **Button**: Full-width grass green "⛏️ START MINING"

### Game Screen
- **Header**: Mining HUD (wood texture)
- **Instructions**: Centered brown text on tan background
- **Victory Banner**: Optional gold ore highlight (when bingo found)
- **Board**: 5×5 grid of stone blocks with 1px gap, centered
- **Container**: Full viewport flex column

### Victory Modal
- **Overlay**: Semi-transparent black backdrop
- **Modal**: Gold gradient card (no border-radius)
- **Content**: Centered with emoji celebration
- **Title**: "VICTORY!" in large uppercase
- **Button**: Full-width grass green "⛏️ Keep Mining"

---

## Accessibility & Usability

### Contrast
- **Text on Grass**: Amber brown (#3C2415) for sufficient contrast
- **Text on Stone**: White for strong visibility
- **Borders**: Dark stone creates clear boundaries

### Interactive States
- **Disabled**: 60% opacity
- **Hover**: Visual lift with drop shadow
- **Active**: Inset shadow for pressed effect
- **Marked/Selected**: Glow animation + color change

### Icons & Emoji
- **Mining pickaxe**: ⛏️ (primary theme icon)
- **Blocks**: 🟫 🟩 ⬜ (block representation)
- **Victory**: ⭐ 💎 (precious rewards)
- **Actions**: 🏠 (back), 💾 (save)

---

## CSS Utilities Reference

### Available Classes
```css
/* Spacing */
.p-1, .p-3, .p-4, .p-6
.px-3, .px-4, .px-6, .px-8
.py-2, .py-3, .py-4
.mb-2, .mb-4, .mb-6, .mb-8

/* Layout */
.flex, .flex-col, .grid, .grid-cols-5
.items-center, .justify-center, .justify-between

/* Typography */
.text-xs, .text-sm, .text-lg, .text-5xl
.font-bold, .font-semibold
.text-center, .text-left

/* Colors */
.bg-grass, .bg-stone, .bg-ore, .bg-dirt, .bg-wood
.text-white, .text-amber-900, .text-amber-800

/* Effects */
.border (3px solid), .shadow-sm, .shadow-xl
.transition-all, .duration-150

/* Special */
.pixel-text (text shadow)
.ore-glow (inset glow for ore blocks)
.marked-square (glowing animation)
```

---

## When Adding New Features

1. **Maintain the blocky aesthetic** - Never use rounded corners or soft shadows for main elements
2. **Use the established color palette** - Stick to the 6 Minecraft block colors
3. **Apply pixel font** - All text should use Roboto Mono
4. **Add appropriate animations** - Use blockPlace or markedGlow patterns
5. **Test contrast** - Ensure text is readable on all backgrounds
6. **Keep uppercase styling** - Important text should be uppercase for authenticity
7. **Add border styling** - Use 3px borders with dark stone color
8. **Use inset shadows** - For 3D depth effect on interactive elements

---

## Files to Reference

- **CSS**: `/app/static/css/app.css` - All Minecraft theme styles
- **Templates**: `/app/templates/components/` - Component markup examples
- **Tests**: `/tests/test_api.py` - Content assertions for theme elements

---

## Example: Adding a New Button

```html
<!-- ✅ Correct: Minecraft themed -->
<button class="bg-grass text-white font-bold px-6 py-3" 
        style="border: 3px solid #558B2F; text-transform: uppercase;">
  ⛏️ NEW ACTION
</button>

<!-- ❌ Avoid: Non-themed -->
<button class="bg-blue-500 text-white rounded-lg px-6 py-3">
  New Action
</button>
```

---

## Troubleshooting Design Issues

| Issue | Solution |
|-------|----------|
| Borders look too thin | Use `border: 3px` instead of `border: 1px` |
| Text hard to read | Apply `pixel-text` class or custom text-shadow |
| Buttons don't feel responsive | Add hover/active state with transform and box-shadow |
| Colors look washed out | Increase saturation, use darker accents |
| No 3D depth | Add inset shadows: `box-shadow: inset 2px 2px 0px rgba(255,255,255,0.3), inset -2px -2px 0px rgba(0,0,0,0.5)` |

