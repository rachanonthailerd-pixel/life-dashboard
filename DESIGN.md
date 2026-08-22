---
name: Life Dashboard
description: A shop's tear-off wall calendar, rebuilt as a personal task ledger
colors:
  board-cream: "#f3e6c8"
  leaf-paper: "#fbf3e1"
  leaf-shade: "#eeddb4"
  press-ink: "#2a1c10"
  ledger-brown: "#6b5c46"
  vermillion-ink: "#a3311a"
  indigo-ink: "#1f4d5c"
  crimson-stamp: "#7a1220"
  gold-seal: "#7d5518"
  gold-rule: "#c99a3d"
  stamp-orange: "#c9722a"
  stamp-orange-edge: "#9c5720"
  crimson-edge: "#5c0e18"
  paper-white: "#ffffff"
typography:
  display:
    fontFamily: "Chonburi, Sarabun, serif"
    fontSize: "22px"
    fontWeight: 400
    lineHeight: 1.2
    letterSpacing: "0.2px"
  heading:
    fontFamily: "Chonburi, Sarabun, serif"
    fontSize: "18px"
    fontWeight: 400
    lineHeight: 1.3
  body:
    fontFamily: "Sarabun, -apple-system, 'Segoe UI', 'Noto Sans Thai', sans-serif"
    fontSize: "14px"
    fontWeight: 500
    lineHeight: 1.4
  label:
    fontFamily: "Sarabun, sans-serif"
    fontSize: "11px"
    fontWeight: 700
    letterSpacing: "0.5px"
rounded:
  none: "0px"
  chip: "3px"
components:
  button-primary:
    backgroundColor: "{colors.stamp-orange}"
    textColor: "{colors.press-ink}"
    rounded: "{rounded.none}"
    padding: "8px 13px"
  button-default:
    backgroundColor: "{colors.leaf-paper}"
    textColor: "{colors.press-ink}"
    rounded: "{rounded.none}"
    padding: "8px 13px"
  button-danger-outline:
    backgroundColor: "transparent"
    textColor: "{colors.crimson-stamp}"
    rounded: "{rounded.none}"
    padding: "8px 13px"
  chip-work:
    backgroundColor: "{colors.vermillion-ink}"
    textColor: "#ffffff"
    rounded: "{rounded.chip}"
    padding: "3px 9px"
  chip-personal:
    backgroundColor: "{colors.indigo-ink}"
    textColor: "#ffffff"
    rounded: "{rounded.chip}"
    padding: "3px 9px"
---

# Design System: Life Dashboard

## Overview

**Creative North Star: "The Shop Calendar"**

Life Dashboard replaced its earlier "Sticker Notebook" identity (flat pastel stickers, no shadows, pedestal-press buttons) with a different everyday object entirely: the printing-house wall calendar that hangs in homes and shopfronts across Thailand — a bold masthead above a tear-off date pad, a thin gold rule separating the two, printed in whatever two house inks the press had on hand. This is a solo daily-use tool, not a marketing surface, so the calendar-shop reference stays functional throughout: every task is a leaf on the pad, and finishing or deleting one visibly tears it free rather than just fading away.

The palette is two deep house inks (a vermillion for "งาน", an indigo for "ส่วนตัว") printed on warm cream paper, with a burnt-orange stamp ink reserved for the one action color and an antique-gold rule marking every heading. Chonburi — a Thai typeface modeled on hand-painted vintage shop-sign lettering — carries the masthead and section-scale headings only; Sarabun, a plain workhorse Thai sans, carries everything read densely (task titles, list rows, form fields), so density and legibility win over expression exactly where the daily task list needs to be scanned fast.

**Key Characteristics:**
- A warm cream board under paper-white "leaves" — every task card, list row, and panel is a leaf on the pad, complete with a die-cut perforation strip at its top edge and a soft paper shadow (never a hard, zero-blur block shadow).
- Two house inks with one job each — vermillion for งาน, indigo for ส่วนตัว — plus a burnt-orange stamp ink for the one action color and a gold rule under every heading.
- Chonburi (vintage Thai shop-sign lettering) at display/heading scale only; Sarabun for every densely-read surface.
- One signature motion: a leaf tears free — translate, rotate, fade — the moment a task is marked done or deleted. No other scattered hover/entrance effects.
- Sharp-cut corners everywhere except the small chip label (3px), which reads as a printed sticker tag.
- Today's date on the calendar wears a printed ring, not a filled highlight.

## Colors

Warm cream paper carries the interface; the two house inks and the gold rule are the only saturated marks.

### Primary
- **Stamp Orange** (`#c9722a`, dark `#e2934f`): the one action color — sign in, add task, save, active tab/filter. Paired with **Press Ink** text (`#2a1c10`, constant in both themes as `--on-primary`) rather than white, since a mid-value orange never clears 4.5:1 against white text in either theme. Pedestal/border shade **Stamp Orange Edge** (`#9c5720`, dark `#b56f2e`).

### Secondary
- **Vermillion Ink** (`#a3311a`, same in both themes): "งาน" (Work) — chips, calendar events. Used only as a solid fill under white text, never as text-on-page, so it doesn't need a lighter dark-mode variant.
- **Indigo Ink** (`#1f4d5c`, same in both themes): "ส่วนตัว" (Personal) — chips, calendar events. Same reasoning as Vermillion Ink.

### Tertiary
- **Gold Seal** (`#7d5518` light, `#d9a94a` dark): reserved for completion — the Done kanban column's top edge and heading, the "เสร็จแล้ว" list heading, and the high-priority badge. A deliberately different role from Gold Rule below: this one carries meaning ("finished"/"important"), the rule is purely decorative.
- **Gold Rule** (`#c99a3d` light, `#d9a94a` dark): the thin divider under every `<h2>` and the calendar masthead, standing in for the "gold rule separating plate from pad" on a real printing-house calendar. Decorative only — never load it with semantic meaning the way Gold Seal carries.
- **Crimson Stamp** (`#7a1220` light text/fill, `#e56a80` dark text): destructive actions and error copy. Because it plays both a text role (needs to brighten in dark mode to stay legible) and a fill role (the delete-confirm "ยืนยัน?" state, which needs to stay dark enough for white text in both themes), the fill role is pinned to a separate constant token, `--danger-fill: #7a1220`, never swapped by theme.

### Neutral
- **Board Cream** (`#f3e6c8`, dark "Board in shadow" `#1a120a`): page background — deliberately kept warm brown in dark mode, never the cool blue-black slate a generic dark theme reaches for.
- **Leaf Paper** (`#fbf3e1`, dark `#241a10`): card, panel, form, and input fill — the pad leaves sitting on the board.
- **Leaf Shade** (`#eeddb4`, dark `#2f2313`): hover tint; also the kanban task-card's resting fill, so a card reads as already lifted off the column.
- **Press Ink** (`#2a1c10`, dark "Cream ink" `#f0e3c8`): all body text and every structural border.
- **Ledger Brown** (`#6b5c46` light, `#b8a684` dark): secondary/muted text (due dates, section meta, field hints).

### Named Rules
**The One Job Per Color Rule.** Every accent has exactly one meaning app-wide (vermillion = work, indigo = personal, gold seal = done/important, stamp orange = the primary action, crimson = danger). Gold Rule is the sole exception, by design: it is decoration, not signal, and must never be asked to carry meaning.

**The 4.5:1 Floor.** Any color paired with text — the text sitting on the color, or the color being the text — clears at least 4.5:1 against its actual background, checked in both themes. `--on-primary` and `--danger-fill` exist specifically because a single theme-swapped token could not satisfy this for every role a color plays.

**The Warm-Dark Rule.** Dark mode stays in the same warm brown-black family as the light board; it never drifts to a cool blue-black "generic dark mode" ground.

## Typography

**Display/Heading Font:** Chonburi (with Sarabun, serif fallback) — a Thai face modeled on hand-painted vintage shop-sign lettering.
**Body/Label Font:** Sarabun (with system sans fallback) — a plain, dense-legible Thai workhorse face.

**Character:** Chonburi supplies the one expressive, "this is a printed shop calendar" voice; Sarabun stays out of the way everywhere the page is read densely. The pairing is deliberately asymmetric — expression at masthead scale, restraint everywhere else — because this is a daily Operate-mode tool, not a poster.

### Hierarchy
- **Display** (Chonburi, 400, 22px, 1.2 line-height): the "Life Dashboard" wordmark only.
- **Heading** (Chonburi, 400, 18px, 1.3 line-height): the add/edit form title and the calendar's month/year label — the two other places content earns a masthead-scale anchor.
- **Body** (Sarabun, 500, 14px, 1.4 line-height): task titles, form fields, buttons, empty-state copy.
- **Label** (Sarabun, 700, 11px, 0.5px tracking, uppercase for section headers): chips, meta text, kanban/list section headers, calendar-cell contents, priority badges.

### Named Rules
**The Masthead-Only Rule.** Chonburi appears only at Display or Heading scale (≥18px). It never appears on densely-repeated content (task titles, list rows, section headers) — a heavy display face at 11–14px repeated down a list fights legibility, which this Operate-mode tool cannot afford.

## Layout

Unchanged from the incumbent structural system: a single centered column, max-width 960px, 16–18px outer padding; the toolbar wraps on narrow viewports; kanban is the one horizontally-scrolling exception (four columns, 200px minimum each, each column additionally capped at 65vh with its own internal vertical scroll beneath a fixed header). This redesign is a visual-world replacement, not a structural one — spacing rhythm and responsive behavior carry over from the prior system unchanged.

## Elevation & Depth

Unlike the prior "Sticker Notebook" world (which banned shadows outright in favor of solid-color pedestals), leaves in this world carry a soft, blurred paper shadow — real paper stacked on a board has thickness, and a printed calendar pad's leaves visibly lift off the backing. Shadows are never hard-offset or zero-blur; they use `--shadow-sm` (cards, panels: `0 2px 6px rgba(20,12,4,.14), 0 1px 2px rgba(20,12,4,.10)`, brightened for dark mode) and `--shadow-btn` (buttons at rest, removed entirely on `:active` to read as a stamp being pressed flat).

### Shadow Vocabulary
- **`--shadow-sm`**: every leaf — list items, task cards, kanban columns, the form, the day-detail panel.
- **`--shadow-btn`**: buttons at rest; cleared on `:active` alongside a `scale(.97)` press and a brightness dip, so pressing a button reads as an ink stamp striking the page rather than a sticker lifting off a pedestal.

### Named Rules
**The Paper-Shadow Rule.** Shadows are always soft and offset (never a flat, zero-blur block shadow) and always attached to a leaf or a button — nothing in the system carries ambient decoration.

## Shapes

Sharp-cut corners everywhere (`--radius: 0px`) — panels, buttons, cards, inputs, and calendar cells stay straight-edged "cut paper" rectangles, consistent with the prior system's shape language but now meaning something different: a printed leaf torn along a straight guillotine cut, not a flat sticker. The one exception is the small chip label (`--radius-chip: 3px`), which reads as a printed tag rather than UI chrome. Every leaf additionally carries a `.leaf` perforation strip — a repeating row of small die-cut holes — along its top edge.

## Components

### Buttons
- **Shape:** 2px solid border, 0 radius, soft resting shadow (`--shadow-btn`).
- **Primary:** Stamp Orange fill, Press Ink text (`--on-primary`, not white), Stamp Orange Edge border.
- **Default:** Leaf Paper fill, Press Ink border/text.
- **Danger-outline:** transparent fill, Crimson Stamp border and text; its "ยืนยัน?" confirming state fills with the constant `--danger-fill`, never the theme-swapped `--danger`.
- **Press:** on `:active`, `transform: scale(.97)`, shadow cleared, brightness dipped — an ink-stamp impression, not a pedestal reveal.
- **Tab/Filter toggles:** borderless, living inside a bordered pill container; active state is a flat Stamp Orange fill with Press Ink text.

### Chips
- **Style:** solid fill (Vermillion for Work, Indigo for Personal), white text, 3px radius, no border.

### Cards / Containers ("Leaves")
- **Corner style:** 0 radius throughout.
- **Background:** Leaf Paper on the Board Cream page; Leaf Shade for a kanban task-card's resting fill.
- **Shadow:** `--shadow-sm` (see Elevation & Depth).
- **Border:** 2px solid Press Ink on every container.
- **Perforation:** every leaf (`.leaf` class) carries a die-cut dot strip along its top edge via a `radial-gradient` pseudo-element.
- **Hover:** flat background shift to Leaf Shade — never a transform or shadow change.
- **Signature motion:** on delete-confirm or marking a task done, the leaf plays a single `tearAway` keyframe (translate + rotate + fade, ~320ms) before being removed — the app's one authored moment; nothing else in the system animates beyond hover/focus/press.

### Inputs / Fields
- **Style:** 2px solid Press Ink border, 0 radius, Board Cream fill.
- **Focus:** themed 3px Stamp Orange `outline`, 2px offset, applied site-wide via `:focus-visible`.
- **Checkbox:** native control re-colored with `accent-color: var(--primary)`.

### Navigation (Tabs / Filters)
Two pill-shaped, 2px-bordered containers holding borderless toggle buttons; active state is a flat Stamp Orange fill, each label pairing a line icon with its Thai text.

### Calendar "Today" Ring
The current day's number wears a 2px Stamp Orange ring (a printed date-stamp), rather than a filled or thick-bordered cell — the one place the calendar cell itself stays visually quiet so the ring reads clearly.

## Do's and Don'ts

### Do:
- **Do** keep every leaf's border 2px solid Press Ink at 0 radius, with a soft `--shadow-sm` — the "leaf on a board" language holds everywhere except the 3px chip.
- **Do** reserve Gold Seal for completion/importance only; keep Gold Rule purely decorative.
- **Do** keep Chonburi at Display/Heading scale only (≥18px) — never on dense repeated content.
- **Do** keep dark mode in the warm brown-black family; never drift to a cool blue-black ground.
- **Do** play the `tearAway` motion on done/delete and nowhere else — it stays meaningful because it stays rare.

### Don't:
- **Don't** use a hard-offset, zero-blur shadow anywhere — every shadow is soft and blurred.
- **Don't** put white text on Stamp Orange (or any primary-fill surface) — use `--on-primary` (Press Ink); white fails contrast against this hue at every value the design uses.
- **Don't** let Vermillion, Indigo, Gold Seal, Crimson, or Stamp Orange mean anything other than their one assigned role.
- **Don't** round a corner beyond the 3px chip exception.
- **Don't** use an emoji or Unicode glyph as a stand-in icon; the existing authored line-icon set carries over unchanged from the prior world.
