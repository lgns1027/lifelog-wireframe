---
name: frontend-design
description: >-
  Use this skill ONLY when the user explicitly requests high-craft UI/UX design,
  specifically mentions keywords like "디자인", "디자인 스킬", "frontend-design", "UI 개편", or asks to redesign a full interface with production-grade aesthetics.
  DO NOT activate this skill for simple bug fixes, minor layout adjustments, basic scripts, backend code, or quick minimal code edits without an explicit visual design request.
---

# Universal Frontend Design & Craftsmanship Engine

A battle-tested standard for generating production-grade frontend interfaces that strictly reject generic "AI slop" (lifeless card grids, cliched purple gradients, timid spacing, and default system typography). Designed for universal application across B2B SaaS, data dashboards, consumer apps, landing pages, and wireframe prototypes.

--------------------------------------------------------------------------------

## 1. Core Philosophy: The Anti-"AI Slop" Mandate

AI-generated interfaces often suffer from a recognizable mediocrity: excessive, hollow negative space; predictable rounded rectangle cards with subtle gray borders; timid color palettes; and generic font stacks. 

### Absolute Prohibitions (절대 금지 패턴)
- ❌ **The Cliched Purple Gradient**: Never default to purple/violet linear gradients on white backgrounds with rounded pill buttons.
- ❌ **Hollow Whitespace ("Toy" UI Syndrome)**: Avoid giant empty margins and oversized paddings that make interfaces look like student mockups rather than dense, professional tools.
- ❌ **Default Font Convergence**: Never default to unconfigured `Inter`, `Roboto`, `Arial`, or system fonts without deliberate pairing and styling.
- ❌ **Flat Box Repeating**: Avoid repeating identical rectangular boxes across the entire screen without hierarchy, asymmetry, or visual rhythm.
- ❌ **Ghost Overlays in Figma**: Dropdown options or modal layers nested deep inside scrolling containers that clip or sink behind sibling frames during HTML-to-Design import.

### The Production Standard (상용 프로덕트 기준)
Every generated screen must look and feel like a shipped product from design-forward leaders (e.g., Stripe, Linear, Toss, Vercel, Supabase, Raycast). It must demonstrate:
- **Intentional Density**: Balanced, purposeful use of every viewport pixel.
- **Semantic Contrast**: Crisp boundary definitions between surfaces, text, and active controls.
- **State Completeness**: Full coverage of realistic user interactions and lifecycle states.

--------------------------------------------------------------------------------

## 2. Design Archetype Selection Matrix (디자인 아키타입 매트릭스)

Before writing a single line of code, commit to **one bold aesthetic direction** tailored to the problem domain. Do not mix competing archetypes.

| Archetype | Best For | Visual Signature | Key Typography & Colors |
| :--- | :--- | :--- | :--- |
| **1. High-Density Enterprise SaaS** | Analytics, B2B dashboards, developer tools, admin portals | Compact data grids, crisp 1px borders, subtle zebra striping, status badges, monospace metrics | Monospace/Geometric (`JetBrains Mono`, `Plus Jakarta Sans`) / Slate & Cool Gray with Emerald/Indigo accents |
| **2. Refined Consumer Fintech** | Banking, personal finance, career lifelogs, premium portals | Polished micro-cards, soft elevated shadows, bold numerical typography, generous contrast | Modern Sans (`Pretendard`, `Outfit`) / Deep Navy, Clean White, Vibrant Cobalt & Mint |
| **3. Modern Editorial & Narrative** | Content platforms, portfolio, thought leadership, landing pages | Large expressive display titles, asymmetric columns, pull quotes, rich divider lines | Serif/Display (`Cinzel`, `Clash Display`, `Newsreader`) + Crisp Sans / Warm Stone, Charcoal, Terracotta |
| **4. Neo-Brutalist & Raw Utility** | Web3, creator tools, experimental apps, youth-focused brands | Thick black borders (2px~3px), hard drop shadows (`box-shadow: 4px 4px 0px #000`), vibrant block colors | Punchy Grotesk (`Syne`, `Space Grotesk`) / High-contrast Yellow, Electric Blue, Raw Black/White |
| **5. Dark Kinetic / Cyber Tech** | AI interfaces, crypto, gaming, developer consoles | Deep dark backgrounds (`#090D16`, `#0A0A0C`), subtle glow borders, glassy backdrops (`backdrop-filter`) | Technical Sans (`Cabinet Grotesk`, `Geist`) / Pitch Black, Cyan/Violet neon accents |
| **6. Warm Humanist / Organic** | Wellness, education, community, life logging, journaling | Soft rounded corners (12px~16px), warm cream/off-white surfaces, calm earthy hues | Humanist Sans/Serif (`Fraunces`, `Plus Jakarta Sans`) / Sand, Warm Olive, Sage, Clay |

--------------------------------------------------------------------------------

## 3. Spatial Hierarchy & The Golden Density Rule (공간 비율 및 고밀도 원칙)

### The Golden Density Rule (골든 덴시티)
A professional interface packs maximum signal with minimum noise. "Clean" does not mean "empty".
- **Compact Density (데이터 집약형)**: Data tables, analytics, management tools. Card padding: `12px~16px`; Gap: `8px~12px`; Line height: `1.4`.
- **Comfortable Density (표준 B2B/B2C)**: Dashboards, profile forms, settings. Card padding: `18px~24px`; Gap: `16px~20px`; Line height: `1.5~1.6`.
- **Editorial Density (랜딩/스토리텔링)**: Hero sections, marketing pages. Padding: `32px~64px`; Gap: `24px~40px`.

### Layout Composition Guidelines
- **Multi-Column Proportions**: Avoid 50/50 splits for complex tasks. Favor asymmetrical ratios like `380px : 1fr` (Control panel vs. Visualization) or `260px : 1fr : 320px` (Nav vs. Workspace vs. Inspector).
- **Surface Elevation**: Distinguish hierarchy through surface tonal shifts (e.g., `#ffffff` card on `#f8fafc` background) and subtle borders (`border: 1px solid #e2e8f0`) rather than heavy drop shadows.

--------------------------------------------------------------------------------

## 4. Universal Typography & CSS Token System

### Typography Pairing Engine (국문/영문 다국어 페어링)
Korean/CJK layouts often suffer from awkward line breaks and uneven optical weights. Always enforce:
```css
/* Korean / CJK Readability Standard */
word-break: keep-all;
overflow-wrap: break-word;
text-rendering: optimizeLegibility;
-webkit-font-smoothing: antialiased;
```

**Recommended Font Stacks (Google Fonts / CDN Ready):**
- **SaaS / UI Standard**: `'Pretendard', 'Plus Jakarta Sans', -apple-system, sans-serif`
- **Display / Expressive**: `'Clash Display', 'Syne', 'Space Grotesk', 'Pretendard', sans-serif`
- **Technical / Metrics**: `'JetBrains Mono', 'Fira Code', 'Pretendard', monospace`

### Universal CSS Token Blueprint
Always declare semantic CSS custom properties at `:root`:
```css
:root {
  /* Surfaces & Canvas */
  --bg-app: #f8fafc;
  --bg-surface: #ffffff;
  --bg-surface-subtle: #f1f5f9;
  --bg-surface-hover: #e2e8f0;

  /* Typography */
  --text-primary: #0f172a;
  --text-secondary: #475569;
  --text-muted: #94a3b8;
  --text-inverse: #ffffff;

  /* Borders & Dividers */
  --border-subtle: #f1f5f9;
  --border-default: #e2e8f0;
  --border-strong: #cbd5e1;

  /* Brand & Accents */
  --accent-primary: #2563eb;
  --accent-primary-hover: #1d4ed8;
  --accent-subtle: #eff6ff;
  --accent-contrast: #ffffff;

  /* Semantic Feedback */
  --status-success: #10b981;
  --status-warning: #f59e0b;
  --status-danger: #ef4444;
  --status-info: #06b6d4;

  /* Geometry & Elevation */
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 12px;
  --radius-pill: 9999px;
  --shadow-card: 0 1px 3px rgba(0, 0, 0, 0.05), 0 1px 2px rgba(0, 0, 0, 0.03);
  --shadow-overlay: 0 10px 25px -5px rgba(0, 0, 0, 0.12), 0 8px 10px -6px rgba(0, 0, 0, 0.08);
}
```

--------------------------------------------------------------------------------

## 5. UI Engineering & Tool-Fidelity Protocol (Figma & Static Renders)

Figma plugins (like HTML to Design), headless browser captures, and static wireframe engines parse the DOM strictly in layout order. Deeply nested popups, dropdowns, and overlays frequently get clipped by parent containers or hidden behind subsequent DOM siblings.

### The Top-Layer Promotion Rule (오버레이 최상위 승격 원칙)
- **DOM Hierarchy**: All dropdown menus, tooltips, popover overlays, and modals must NOT be nested inside an early sibling element. Instead, place them as the **last child element of the relative boundary container** (e.g., the `.ui-card` or main panel) or at the document body level.
- **Explicit Positioning**: When generating static or wireframe states, give open overlays explicit absolute coordinates (`top`, `left`, `width`, `z-index: 1000`) so they render seamlessly on top in both browsers and Figma.

### Data Visualization & SVG Chart Standards
- **Zero-Overlap Guarantee**: Never place floating absolute text directly over dynamic SVG path coordinates without dedicated background badges or collision calculation.
- **ViewBox & Responsiveness**: Every SVG must feature an explicit `viewBox="0 0 W H"` and `width="100%" height="auto"` or fixed height with `preserveAspectRatio="xMidYMid meet"`.
- **Legend & Metric Cards**: Separate summary KPI cards and chart legends from the drawing canvas. Keep chart lines clean with clear dotted guides and high-contrast labels.

--------------------------------------------------------------------------------

## 6. Implementation Dual Guide: Pure HTML/CSS vs. Tailwind/React

### Option A: Pure HTML/CSS (Static Wireframes & 100% Tool Fidelity)
Use when building standalone HTML wireframes, prototypes, or design artifacts:
- **0% JavaScript Dependency**: Implement interactive feel via CSS-only states (`:hover`, `:active`, `:focus-within`, custom checkbox/radio hacks).
- **Explicit Dimensions**: Provide clear min-width, max-width, or CSS Grid track definitions (`grid-template-columns: 380px 1fr`) to prevent collapsing.
- **Self-Contained Styling**: Embed CSS in `<style>` blocks for single-file portability and one-click Figma import.

### Option B: Modern React & Tailwind CSS (Production Web Applications)
Use when building scalable web applications and component systems:
- **Consistent Tokens**: Map semantic variables to Tailwind classes (`bg-surface`, `text-primary`, `border-subtle`).
- **Compound Components**: Group related elements logically (e.g., `<Select.Root>`, `<Select.Trigger>`, `<Select.Content>`).
- **Headless Accessible Primitives**: Prefer Radix UI / Headless UI patterns for accessible keyboard navigation and focus management.

--------------------------------------------------------------------------------

## 7. Component Craftsmanship & Completeness Checklist

Every component must satisfy this production-grade quality checklist before being considered complete:

1. **State Completeness**:
   - [ ] **Default**: Clear baseline presentation.
   - [ ] **Hover / Focus**: Distinct contrast shift, subtle border/background transition (`150ms ease`).
   - [ ] **Active / Selected**: Unmistakable indicator (check mark, high-contrast fill, or distinct outline).
   - [ ] **Disabled**: Low opacity (`0.5`), cursor not-allowed, preserved layout.
   - [ ] **Empty State**: Contextual icon/emoji, helpful explanation, primary CTA button (never leave an empty white card).
2. **Form & Input Depth**:
   - [ ] Labels have explicit associations and helper micro-copy.
   - [ ] Complex options include secondary metadata (e.g., title + badge + description).
   - [ ] Search inputs include contextual search chips/recommendations.
3. **Contrast & Legibility**:
   - [ ] Minimum contrast ratio of 4.5:1 for body text against backgrounds.
   - [ ] Visual indicators do not rely on color alone (use icons, tags, or weights alongside color).