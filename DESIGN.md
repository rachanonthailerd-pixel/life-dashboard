---
name: Life Dashboard
description: A strip of shop-front neon signage at night, rebuilt as a personal task board
colors:
  night-ground: "#0b0d16"
  sign-panel: "#141726"
  sign-panel-lit: "#1c2036"
  neon-white: "#eef1fb"
  unlit-gray: "#8b92ac"
  frame-dim: "#2a2f45"
  cyan-tube: "#2dd4f0"
  magenta-tube: "#f43f8e"
  crimson-tube: "#ff4d5e"
  green-tube: "#39e67a"
  amber-tube: "#ffcc33"
  amber-tube-edge: "#cc9f1f"
  crimson-tube-edge: "#cc3040"
typography:
  display:
    fontFamily: "Kanit, Mitr, sans-serif"
    fontSize: "22px"
    fontWeight: 700
    lineHeight: 1.2
    letterSpacing: "0.2px"
  heading:
    fontFamily: "Kanit, sans-serif"
    fontSize: "18px"
    fontWeight: 600
    lineHeight: 1.3
  body:
    fontFamily: "Mitr, -apple-system, 'Segoe UI', 'Noto Sans Thai', sans-serif"
    fontSize: "14px"
    fontWeight: 500
    lineHeight: 1.4
  label:
    fontFamily: "Mitr, sans-serif"
    fontSize: "11px"
    fontWeight: 700
    letterSpacing: "0.5px"
rounded:
  chip: "999px"
  panel: "10px"
  sm: "6px"
components:
  button-primary:
    backgroundColor: "{colors.amber-tube}"
    textColor: "{colors.night-ground}"
    rounded: "{rounded.panel}"
    padding: "8px 13px"
  button-default:
    backgroundColor: "{colors.sign-panel}"
    textColor: "{colors.neon-white}"
    rounded: "{rounded.panel}"
    padding: "8px 13px"
  button-danger-outline:
    backgroundColor: "transparent"
    textColor: "{colors.crimson-tube}"
    rounded: "{rounded.panel}"
    padding: "8px 13px"
  chip-work:
    backgroundColor: "transparent"
    textColor: "{colors.cyan-tube}"
    rounded: "{rounded.chip}"
    padding: "3px 10px"
  chip-personal:
    backgroundColor: "transparent"
    textColor: "{colors.magenta-tube}"
    rounded: "{rounded.chip}"
    padding: "3px 10px"
---

# Design System: Life Dashboard

## Overview

**Creative North Star: "Neon Signage"**

Life Dashboard's second full redesign replaced "The Shop Calendar" (a printing-house tear-off pad — warm cream paper, gold rule, house inks) with an entirely different material: a strip of shop-front neon tube signage seen at night. This is a solo daily-use tool, not a marketing surface, so the reference stays functional — every task is a sign, lit or unlit, and finishing or deleting one plays a brief power-off flicker before it's gone.

The palette is a near-black night ground carrying two neon tube colors with one job each — electric cyan for "งาน", hot magenta for "ส่วนตัว" — plus an amber "OPEN sign" color for the one primary action and a green tube reserved for done/success. An early build pass leaned on blurred colored glow (text-shadow/box-shadow halos) to sell the neon read; the mechanical detector flagged every instance as the generic "AI-generated dark UI" cliché, and rather than merely dimming it, every glow was cut. The shipped system carries its signage identity entirely through saturated color, 1.5px outline, and shape (chips are colored text on a faintly tinted ground, never a solid fill; corners are gently rounded — a neon tube bends, it doesn't cut square) with zero blur anywhere. Kanit, a bold geometric Thai face with real signage character, carries the masthead and every heading; Mitr, a plain workhorse Thai sans, carries everything read densely.

**Key Characteristics:**
- A near-black night ground under dark panel cards — no paper, no cream, no gold rule; this world is screen-native and nocturnal, committed to a single always-dark theme with no light-mode variant.
- Two neon tube colors with one job each — cyan for งาน, magenta for ส่วนตัว — plus amber for the one primary action and green for done/success.
- Zero blur-based glow anywhere. Identity is carried by saturated color, 1.5px outline, and shape alone — a deliberate correction after the detector caught the initial pass's colored halos as a known slop pattern.
- Chips are colored text on a faintly tinted transparent ground, never a solid color fill with white text.
- Moderate rounded corners (10px panels, fully pill-shaped chips) — a bent neon tube, not a cut-paper edge.
- One signature motion: a task's sign flickers (rapid opacity oscillation) and powers off the moment it's marked done or deleted.

## Colors

A near-black night ground carries the interface; the neon tube colors are the only saturated marks, and they never blur.

### Primary
- **Amber Tube** (`#ffcc33`): the one action color — sign in, add task, save, active tab/filter. Paired with **Night Ground** text (`#0b0d16`, the `--on-primary` token) rather than white, since only a very dark ink clears 4.5:1 against this bright a yellow. Pedestal/border shade **Amber Tube Edge** (`#cc9f1f`).

### Secondary
- **Cyan Tube** (`#2dd4f0`): "งาน" (Work) — chip text/outline, calendar events. Rendered as colored text on a transparent, faintly tinted ground (`rgba(45,212,240,.08)`), never a solid fill.
- **Magenta Tube** (`#f43f8e`): "ส่วนตัว" (Personal) — same treatment as Cyan Tube. Also the wordmark's own color, since the heart-shaped sign icon in the masthead is the one place a single accent gets to be decorative rather than semantic.

### Tertiary
- **Green Tube** (`#39e67a`): reserved for completion — the Done kanban column's border and heading, the "เสร็จแล้ว" list heading, and the high-priority badge.
- **Crimson Tube** (`#ff4d5e`): destructive actions and error copy only. Its confirming-delete fill state (`--danger-fill`) is the same value — with only one theme to satisfy, danger doesn't need the light/dark split the prior two worlds required.

### Neutral
- **Night Ground** (`#0b0d16`): page background. The one and only ground value — this world never lightens for a "light mode," because neon signage is an inherently nocturnal material.
- **Sign Panel** (`#141726`): card, panel, form, and input fill.
- **Sign Panel Lit** (`#1c2036`): hover tint; the kanban task-card's resting fill.
- **Neon White** (`#eef1fb`): all body text.
- **Unlit Gray** (`#8b92ac`): secondary/muted text — due dates, section meta, field hints; reads as a sign that isn't switched on.
- **Frame Dim** (`#2a2f45`): the neutral 1.5px border every panel, card, button, and input carries at rest — an unlit sign frame, never colored unless the element itself is semantically cyan/magenta/green/crimson/amber.

### Named Rules
**The One Job Per Color Rule.** Every neon color has exactly one meaning app-wide (cyan = work, magenta = personal, green = done/important, amber = the primary action, crimson = danger). The wordmark's magenta is the sole decorative exception, and it borrows Personal's exact hue rather than inventing a new one.

**The 4.5:1 Floor.** Any color paired with text clears at least 4.5:1 against its actual background. `--on-primary` exists because white text fails against Amber Tube at every value this design uses.

**The No-Glow Rule.** No `text-shadow` or colored `box-shadow` blur appears anywhere in this system. An early pass used both to sell the "neon" read and the mechanical detector flagged it as the generic AI-dark-UI cliché; the fix was to cut every instance, not thin them. Depth and identity come from saturated color, a 1.5px outline, and shape only.

## Typography

**Display/Heading Font:** Kanit (with Mitr, sans-serif fallback) — a bold, geometric Thai face with real signage character.
**Body/Label Font:** Mitr (with system sans fallback) — a plain, dense-legible Thai workhorse face.

**Character:** Kanit supplies the one expressive "this is a lit sign" voice at masthead and heading scale; Mitr stays out of the way everywhere the page is read densely. As in the prior world, expression is deliberately rationed to a small set of anchors so the daily task list stays scannable.

### Hierarchy
- **Display** (Kanit, 700, 22px, 1.2 line-height): the "Life Dashboard" wordmark only, set in Magenta Tube.
- **Heading** (Kanit, 600, 18px, 1.3 line-height): the add/edit form title and the calendar's month/year label.
- **Body** (Mitr, 500, 14px, 1.4 line-height): task titles, form fields, buttons, empty-state copy.
- **Label** (Mitr, 700, 11px, 0.5px tracking, uppercase for section headers): chips, meta text, kanban/list section headers, calendar-cell contents, priority badges.

### Named Rules
**The Masthead-Only Rule.** Kanit appears only at Display or Heading scale (≥18px); it never appears on densely-repeated content, which this Operate-mode tool cannot afford to make less legible.

## Layout

Unchanged from the incumbent structural system across both prior worlds: a single centered column, max-width 960px, 16–18px outer padding; the toolbar wraps on narrow viewports; kanban is the one horizontally-scrolling exception (four columns, 200px minimum each, each additionally capped at 65vh with its own internal vertical scroll beneath a fixed header). This redesign, like the one before it, replaces the visual world only — spacing rhythm and responsive behavior carry over unchanged.

## Elevation & Depth

Flat panels on a flat ground — no shadow, no blur, no ambient glow anywhere in the shipped system. Depth and hierarchy come entirely from the 1.5px Frame Dim border (neutral at rest, colored only when an element is semantically cyan/magenta/green/crimson/amber) and from a small, restrained neutral box-shadow (`--shadow-sm`, `--shadow-btn`) that lifts panels and buttons off the ground without any color in it.

### Named Rules
**The No-Glow Rule.** See Colors. Restated here because it is fundamentally an elevation decision, not just a color one: this system draws depth with borders and neutral shadow only, the same discipline the prior "Shop Calendar" world applied to paper shadows, now applied to a material that is far more tempting to render with cliché colored blur.

## Shapes

Moderately rounded corners throughout (`--radius: 10px` for panels, buttons, cards, and the top-level tab/filter pill container) — a bent neon tube, not a cut-paper edge, and a deliberate departure from both prior worlds' sharp corners. Elements nested one level inside a rounded container (individual tab/filter buttons, form inputs, calendar cells, scrollbar thumbs) use the smaller `--radius-sm: 6px` step, so a nested corner never reads as sharper or more rounded than its parent's curve. The chip is the one shape taken further: fully pill-shaped (`--radius-chip: 999px`), reading as a closed loop of tube glass around its label. The calendar's today-ring is a plain circle (`border-radius: 50%`), the universal CSS idiom for a round badge rather than a step in this scale.

## Components

### Buttons
- **Shape:** 1.5px solid Frame Dim border, 10px radius, small neutral resting shadow.
- **Primary:** Amber Tube fill, Night Ground text (`--on-primary`, not white), Amber Tube Edge border.
- **Default:** Sign Panel fill, Neon White text, Frame Dim border.
- **Danger-outline:** transparent fill, Crimson Tube border and text; its "ยืนยัน?" confirming state fills solid with Crimson Tube (`--danger-fill`).
- **Press:** on `:active`, `transform: scale(.97)`, shadow cleared, brightness dipped.
- **Tab/Filter toggles:** borderless, living inside a bordered pill container; active state is a flat Amber Tube fill with Night Ground text — no glow.

### Chips
- **Style:** colored text (Cyan for Work, Magenta for Personal) on a faintly tinted transparent ground, 1.5px matching-color border, fully pill-shaped (999px radius) — never a solid fill.

### Cards / Containers
- **Corner style:** 10px radius throughout.
- **Background:** Sign Panel on the Night Ground page; Sign Panel Lit for a kanban task-card's resting fill and any hover state.
- **Shadow:** small, neutral, uncolored (`--shadow-sm`) — see Elevation & Depth.
- **Border:** 1.5px solid Frame Dim on every container at rest; colored only for a semantically-meaningful state (the Done kanban column's Green Tube border).
- **Hover:** border brightens to Unlit Gray, background shifts to Sign Panel Lit — never a transform or colored glow.
- **Signature motion:** on delete-confirm or marking a task done, the card plays a single `powerOff` keyframe (rapid opacity flicker, ~400ms) before being removed — the app's one authored moment.

### Inputs / Fields
- **Style:** 1.5px solid Frame Dim border, 6px radius (`calc(var(--radius) - 4px)`), Night Ground fill.
- **Focus:** themed 3px Amber Tube `outline`, 2px offset, applied site-wide via `:focus-visible`.
- **Checkbox:** native control re-colored with `accent-color: var(--primary)`.

### Navigation (Tabs / Filters)
Two pill-shaped, 1.5px-bordered containers holding borderless toggle buttons; active state is a flat Amber Tube fill, each label pairing a line icon with its Thai text.

### Calendar "Today" Ring
The current day's number wears a 2px Amber Tube ring — a printed date-stamp reused from the prior world's grammar, now unlit (no glow) so it reads as an outline marker rather than a lit indicator.

## Do's and Don'ts

### Do:
- **Do** keep every panel's border 1.5px solid Frame Dim (or the matching semantic color) at 10px radius, with a small neutral shadow — never colored.
- **Do** reserve Green Tube for completion/importance only.
- **Do** keep Kanit at Display/Heading scale only (≥18px) — never on dense repeated content.
- **Do** play the `powerOff` flicker on done/delete and nowhere else — it stays meaningful because it stays rare.
- **Do** render chips as colored text on a faint tint, never a solid fill.

### Don't:
- **Don't** add a `text-shadow` or colored `box-shadow` blur anywhere in this system — it was tried, flagged by the detector as slop, and removed; it does not come back.
- **Don't** put white text on Amber Tube (or any primary-fill surface) — use `--on-primary` (Night Ground); white fails contrast against this hue.
- **Don't** let Cyan, Magenta, Green, Crimson, or Amber mean anything other than their one assigned role (the wordmark's Magenta is the sole named exception).
- **Don't** ship a light-mode variant — this world is committed to always-dark.
- **Don't** use an emoji or Unicode glyph as a stand-in icon; the existing authored line-icon set carries over unchanged from the prior worlds.
