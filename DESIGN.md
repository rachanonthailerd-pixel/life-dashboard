---
name: Life Dashboard
description: A chunky, shadowless calendar/kanban/list dashboard styled like pages from a sticker notebook
colors:
  sunny-amber: "#ffc23c"
  sunny-amber-edge: "#dd9a1e"
  sky-sherbet: "#3a86ff"
  bubblegum-pink: "#ef5da8"
  minty-fresh: "#2ec4b6"
  cherry-fizz: "#ef476f"
  cherry-fizz-edge: "#c62f52"
  vanilla-cream: "#fdf5e6"
  paper-white: "#fffdf8"
  butter-cream: "#fff1d6"
  cocoa-ink: "#2d2a3a"
  dusty-grape: "#8a8398"
  on-accent: "#ffffff"
typography:
  display:
    fontFamily: "Prompt, -apple-system, 'Segoe UI', 'Noto Sans Thai', sans-serif"
    fontSize: "22px"
    fontWeight: 700
    lineHeight: 1.2
    letterSpacing: "0.2px"
  heading:
    fontFamily: "Prompt, sans-serif"
    fontSize: "18px"
    fontWeight: 700
    lineHeight: 1.3
  body:
    fontFamily: "Prompt, -apple-system, 'Segoe UI', 'Noto Sans Thai', sans-serif"
    fontSize: "14px"
    fontWeight: 500
    lineHeight: 1.4
  label:
    fontFamily: "Prompt, sans-serif"
    fontSize: "11px"
    fontWeight: 700
    letterSpacing: "0.5px"
rounded:
  none: "0px"
  chip: "4px"
components:
  button-primary:
    backgroundColor: "{colors.sunny-amber}"
    textColor: "{colors.cocoa-ink}"
    rounded: "{rounded.none}"
    padding: "8px 13px"
  button-default:
    backgroundColor: "{colors.paper-white}"
    textColor: "{colors.cocoa-ink}"
    rounded: "{rounded.none}"
    padding: "8px 13px"
  button-danger-outline:
    backgroundColor: "transparent"
    textColor: "{colors.cherry-fizz}"
    rounded: "{rounded.none}"
    padding: "8px 13px"
  chip-work:
    backgroundColor: "{colors.sky-sherbet}"
    textColor: "#ffffff"
    rounded: "{rounded.chip}"
    padding: "3px 9px"
  chip-personal:
    backgroundColor: "{colors.bubblegum-pink}"
    textColor: "#ffffff"
    rounded: "{rounded.chip}"
    padding: "3px 9px"
---

# Design System: Life Dashboard

## Overview

**Creative North Star: "The Sticker Notebook"**

Life Dashboard is a single-user daily tool, not a marketing surface, so it commits to the opposite of a corporate SaaS dashboard: a warm cream "page" covered in chunky, hand-outlined stickers rather than a slick glass panel with ambient shadows. Every panel, button, and card is drawn with a solid 2px ink border and a flat fill — no blur, no soft elevation, nothing ambient. The one place depth appears is a button press: each button sits on a solid-color pedestal it physically pushes into on click, like pressing a real sticker down onto paper.

The palette is small and each color carries exactly one meaning — sky blue for work, bubblegum pink for personal, mint only for "done," amber for the one action on screen, cherry only for delete. Nothing decorative borrows an accent color. Icons are a small hand-drawn line set (folded note, list, columns, calendar grid, sparkle, briefcase, heart) that replaced an earlier pass built on emoji — the notebook illusion breaks the moment a real emoji glyph shows up next to a drawn one, so the set stays one consistent stroke weight throughout.

**Key Characteristics:**
- Flat and shadowless — depth comes from borders and pedestals, never `box-shadow`.
- 2px solid "ink" borders and 0 border-radius everywhere except the 4px chip.
- Chunky buttons that visibly press down 3px on click (transform-only, no layout-property animation).
- A two-tone candy palette where every accent color has exactly one job.
- Prompt typeface throughout — one face that renders Thai and Latin with matching rounded geometry.
- A small authored 24×24 line-icon set; no emoji anywhere in the interface.

## Colors

Warm cream "paper" neutrals carry the interface; saturated candy accents appear only when they're communicating something specific.

### Primary
- **Sunny Amber** (`#ffc23c`, dark `#ffd166`): the one action color — sign in, add task, save, and the active tab/filter highlight. Its pedestal (the solid edge beneath the button) is **Amber Caramel** (`#dd9a1e`, dark `#cc9a35`).

### Secondary
- **Sky Sherbet** (`#3a86ff`, dark `#6fb2ff`): "งาน" (Work) — chips, calendar events tagged Work.
- **Bubblegum Pink** (`#ef5da8`, dark `#ff8ecb`): "ส่วนตัว" (Personal) — chips, calendar events tagged Personal.

### Tertiary
- **Minty Fresh** (`#2ec4b6`, dark `#56e0cf`): reserved exclusively for completion — the Done kanban column's top edge and heading, and the "เสร็จแล้ว" list heading. It appears nowhere else, so it stays a genuine "finished" signal rather than decoration.
- **Cherry Fizz** (`#ef476f`, dark `#ff7a9c`): destructive actions only (delete buttons, error text). Pedestal shade **Cherry Deep** (`#c62f52`, dark `#d65878`).

### Neutral
- **Vanilla Cream** (`#fdf5e6`, dark "Midnight Grape" `#211d36`): page background.
- **Paper White** (`#fffdf8`, dark "Plum Velvet" `#2b2547`): card, panel, and input fill.
- **Butter Cream** (`#fff1d6`, dark "Blackberry Tint" `#342c58`): hover tint; also the task-card fill inside a kanban column, so a card visibly lifts off its column without a shadow.
- **Cocoa Ink** (`#2d2a3a`, dark "Cream Foam" `#f5efe0`): all body text and every structural border.
- **Dusty Grape** (`#8a8398`, dark "Lilac Mist" `#b0a8c4`): secondary/muted text.
- **On-Accent White** (`#ffffff`, same in both themes): text set directly on a saturated accent fill — chips and calendar task chips only.

### Named Rules
**The One Job Per Color Rule.** Every accent maps to exactly one meaning app-wide (blue = work, pink = personal, mint = done, amber = the primary action, cherry = danger). If one of these colors appears on screen, it is communicating that specific thing — never decoration.

## Typography

**Display / Body Font:** Prompt (with `-apple-system, "Segoe UI", "Noto Sans Thai", sans-serif` fallback)

**Character:** Rounded and a little chunky — friendly rather than technical, and still legible at the small sizes a dense task list needs. Chosen specifically because it renders Thai and Latin script with matching geometry, which a Latin-only display face could not do for this bilingual interface.

### Hierarchy
- **Display** (700, 22px, 1.2 line-height): the "Life Dashboard" wordmark only.
- **Heading** (700, 18px, 1.3 line-height): the calendar's month/year label — the one place content needs a second-level anchor.
- **Body** (500, 14px, 1.4 line-height): task titles, form fields, buttons, empty-state copy — the working size for anything read or clicked.
- **Label** (700, 11px, 0.5px tracking, uppercase for section headers): chips, meta text, kanban/list section headers, calendar-cell contents — dense secondary information.

### Named Rules
**The Four-Size Rule.** Exactly four font sizes exist app-wide (11 / 14 / 18 / 22px, each token-backed via `--fs-*`). A new component reaches for one of these; it does not introduce a fifth.

## Layout

A single centered column, max-width 960px, 16–18px outer padding. The toolbar (view tabs, project filters, add button) wraps on narrow viewports rather than truncating. Kanban is the one horizontally-scrolling exception — four columns, 200px minimum each — so it stays usable on a phone without collapsing to a single column. Spacing runs loose rather than tight (8–20px between related elements): this is a personal daily-use tool, not a data-dense console, so every task gets room to read as its own card rather than a packed row.

## Elevation & Depth

No `box-shadow` appears anywhere in the system — an earlier pass used hard-offset block shadows on every card and button, and it was deliberately replaced with a flatter treatment. Depth now comes from two mechanisms only: every surface carries a solid 2px ink border, so containment reads from outline rather than cast light; and every button rests on a solid-color pedestal (a static, fixed-size pseudo-element, not a shadow) that it visually presses into on `:active` via a 3px `transform: translateY`. Nothing in the system is ambient — depth appears only as a direct response to a click.

### Named Rules
**The No-Shadow Rule.** `box-shadow` does not appear anywhere in this system. Depth is drawn with borders and solid-color pedestals only.

## Shapes

Zero border-radius everywhere — panels, buttons, cards, inputs, and calendar cells are sharp "cut paper" rectangles — except the small pill-shaped chip (4px), which reads as a printed sticker label rather than UI chrome, reinforcing the notebook metaphor.

## Components

### Buttons
- **Shape:** 2px solid border, 0 radius, no shadow.
- **Primary:** Sunny Amber fill, Cocoa Ink text and border, Amber Caramel pedestal.
- **Default:** Paper White fill, Cocoa Ink border/text/pedestal.
- **Danger-outline:** transparent fill, Cherry Fizz border and text, Cherry Deep pedestal — reserved for delete actions.
- **Press:** on `:active`, the button translates down 3px onto its pedestal (`transform` only — `border-width`, `padding`, and other layout properties never animate).
- **Tab / Filter toggles:** a borderless variant living inside a bordered pill container; the active state is a flat Sunny Amber fill with no pedestal, since these are selectors, not "pressable" actions.

### Chips
- **Style:** solid fill (Sky Sherbet for Work, Bubblegum Pink for Personal), white text, 4px radius, no border — reads as a printed sticker label.

### Cards / Containers
- **Corner style:** 0 radius throughout (task cards, list items, calendar cells, kanban columns, the add-task form).
- **Background:** Paper White on the Vanilla Cream page; Butter Cream for a task-card's fill inside its kanban column.
- **Shadow strategy:** none — see Elevation & Depth.
- **Border:** 2px solid Cocoa Ink on every container, no exceptions.
- **Hover:** a flat background shift to Butter Cream — never a transform or shadow.

### Inputs / Fields
- **Style:** 2px solid Cocoa Ink border, 0 radius, Vanilla Cream fill.
- **Focus:** a themed 3px Sunny Amber `outline`, 2px offset — applied site-wide via `:focus-visible`, not just on inputs.
- **Checkbox:** the native control re-colored with `accent-color: var(--primary)` rather than a custom-built control.

### Navigation (Tabs / Filters)
Two pill-shaped, 2px-bordered containers (view tabs, project filters) holding borderless toggle buttons; the active state is a flat amber fill, and every label pairs a small line icon with its Thai text.

### Icon System (signature component)
A small authored set of 24×24 line icons (2px stroke, round caps and joins, `currentColor`) replaced every emoji that used to stand in for meaning: a folded-corner note for the wordmark, list/columns/calendar-grid for the three views, a sparkle/briefcase/heart for the three filters, a cross for "add." One consistent stroke weight across the set is the point — pairing a drawn icon with an emoji anywhere would break the notebook illusion immediately.

## Do's and Don'ts

### Do:
- **Do** keep every border 2px solid Cocoa Ink (or the matching accent) at 0 radius — the "cut paper" language holds everywhere except the chip.
- **Do** reserve Minty Fresh for completion states only.
- **Do** animate button presses with `transform` against a static pedestal — never `width`, `height`, `padding`, `margin`, or `border-width`.
- **Do** draw new icons in the same 24×24, 2px-stroke, round-cap line style as the existing set.
- **Do** stay inside the four-size type scale (11 / 14 / 18 / 22px).

### Don't:
- **Don't** add `box-shadow` anywhere — this system rejected it deliberately in favor of borders and pedestals.
- **Don't** use an emoji or other Unicode glyph as a stand-in icon; draw one in the authored set instead.
- **Don't** round a corner beyond the 4px chip exception.
- **Don't** let amber, blue, pink, mint, or cherry mean anything other than their one assigned role.
