# Design

## Color Strategy

Restrained. Deep navy base, single yellow accent used at ≤10% coverage. All other surfaces are tinted neutrals derived from the brand blue.

## Color Palette

| Token | Value | Role |
|---|---|---|
| `--background` | `#000F1E` | Page & shell background |
| `--surface-1` | `#0D1E35` | Card and panel backgrounds |
| `--surface-2` | `#1A2C47` | Hover surfaces, elevated panels |
| `--surface-hover` | `#243656` | Active/pressed states |
| `--foreground` | `#FFFFFF` | Primary text |
| `--muted-foreground` | `#939598` | Secondary text, captions |
| `--border` | `#1A2C47` | Dividers, outlines, input borders |
| `--yellow-500` | `#FFFF00` | Brand accent — CTA, active states, highlights |
| `--yellow-600` | `#E6E600` | Hover state for yellow elements |
| `--deep-blue-800` | `#000F1E` | Text on yellow surfaces |

## Typography

- **Font**: Plus Jakarta Sans (Google Fonts) — 300, 400, 500, 600, 700, 800
- **Page title**: 52px / 800 / -0.025em tracking / line-height 1.1
- **Section title**: 22px / 700 / -0.015em tracking
- **Body**: 16px / 400 / line-height 1.6 / max 65ch
- **Small / label**: 13px / 500
- **Eyebrow**: 11px / 700 / uppercase / 0.12em tracking / yellow-500 at 70%
- **Monospace**: system-ui monospace for tokens and code

## Elevation

Three surfaces only. No arbitrary `box-shadow` values.
- **Level 0**: `--background` — shell
- **Level 1**: `--surface-1` + `1px solid --border` — cards, panels
- **Level 2**: `--surface-2` — hover state, raised elements

Shadows are tinted to brand hue (deep blue), never pure black.

## Spacing Scale

4px base. Steps: 4, 8, 12, 16, 20, 24, 28, 32, 40, 48, 56, 64, 80.

## Border Radius

- `--radius-s`: 6px — inputs, badges, small elements
- `--radius-m`: 10px — default cards, buttons
- `--radius-l`: 16px — large containers, feature cards
- `--radius-pill`: 999px — pills, tags

## Motion

- Duration: 220ms standard, 280ms for page transitions
- Easing: `cubic-bezier(0.16, 1, 0.3, 1)` (ease-out-expo) for all entrances
- Easing: `cubic-bezier(0.2, 0, 0, 1)` for interactive state changes
- Respect `prefers-reduced-motion: reduce` — disable all transforms/animations

## Components

- **Nav link active**: gradient background left-to-right, 2px yellow left border, 600 weight
- **Card**: surface-1, border, radius-l, tinted shadow, yellow accent glow on hover
- **CTA button**: yellow-500 fill, deep-blue text, 700 weight, radius-m, glow on hover
- **Callout**: surface-1 bg, full yellow border (all sides), not a side stripe
- **Phase banner**: full yellow top border strip, gradient background
- **Eyebrow**: yellow-500 at 70% opacity, uppercase, 11px, 700 weight

## Anti-patterns

- Side-stripe borders wider than 1px as the sole accent (absolute ban)
- Gradient text (`background-clip: text`)
- Glassmorphism used decoratively or as the default for all surfaces
- Pure `#000000` or `#ffffff` — always tint neutrals
- Identical card grids with icon + heading + text repeated 6+ times without variation
