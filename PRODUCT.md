# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Solo use by the product owner (the user themselves) — no shared/multi-user or family access planned. They struggle with staying organized and following up on commitments, and want work and personal life kept clearly separated rather than blended into one undifferentiated list. Used daily across a Windows PC/laptop and a mobile phone (Android/iOS) browser.

## Product Purpose

A personal life-management dashboard that gives one unified view of tasks and events as a calendar, a kanban board, and a list — always split cleanly between "งาน" (work) and "ส่วนตัว" (personal) — so nothing gets lost and every commitment can be tracked through to done. Success means the owner always knows what's due, what's in progress, and never misses a time-boxed commitment.

## Positioning

Unlike using Google Calendar/Tasks/Sheets directly (three disconnected native UIs) or a paid tool like Notion/Trello, this is one custom-designed dashboard unifying all three views, at zero added cost, with zero extra login for daily use — all data lives in the owner's own free Google account and is reachable from any device via a plain URL, no app install and no Claude or third-party account required to use it day to day.

## Operating Context

Daily use is direct interaction with the web app itself (add/edit/delete tasks, move kanban status, browse the calendar) on a Windows PC/laptop and a mobile browser — not mediated through chat/assistant tooling. Sign-in is periodic Google OAuth (the Cloud OAuth consent screen is intentionally kept in Testing mode, so re-consent is needed roughly every 7 days) against a dedicated Google account, kept deliberately separate from any other Google account or Claude/MCP connector the owner uses elsewhere.

## Capabilities and Constraints

- Three synchronized views — List, Kanban (Backlog / Todo / Doing / Done), Calendar — each filterable by All / Work / Personal.
- A Google Sheet ("Life Dashboard Master Board") is the single source of truth for task data (id, title, project, status, due, priority, notes, calendarEventId); no other copy of task state exists.
- A task with a specific time (not just a date) mirrors out to a real Google Calendar event on one of two auto-created calendars ("งาน (Life Dashboard)", "ส่วนตัว (Life Dashboard)") so native phone notifications fire; date-only tasks stay app-only.
- No backend/server: pure client-side OAuth via the Google Identity Services token client, calling the Sheets/Calendar/Drive REST APIs directly from the browser.
- Static single-file site (`index.html`), no build step, no framework, hosted free on GitHub Pages from a public repo.
- Must stay within Google API free-tier quotas and GitHub Pages' free hosting — no paid service anywhere in the stack.
- Hard constraint: this system's Google account, Cloud project, and OAuth client must stay fully independent from any Google account bound to a Claude/MCP connector.

## Evidence on Hand

None — a personal-use tool with no testimonials, case studies, or pricing to show; nothing here should be fabricated.

## Product Principles

1. Zero added cost — every dependency stays on a free tier (Google APIs, GitHub Pages).
2. Zero extra login for daily use — no Claude or third-party account beyond the owner's own Google account.
3. One data source of truth — the Google Sheet; no duplicated state, so views never disagree across devices.
4. Real notifications where they matter — time-boxed commitments must reach the native phone calendar, not just live inside the web app.
5. Clear work/personal separation — every view, color, and filter respects the same two-category split.

## Accessibility & Inclusion

No product-specific accessibility requirement established; general good practice only.
