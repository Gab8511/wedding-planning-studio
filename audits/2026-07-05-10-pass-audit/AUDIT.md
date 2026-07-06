# VowSuite 10-Pass Product Audit

Date: 2026-07-05  
App: https://gab8511.github.io/wedding-planning-studio/  
Version observed: v1.1.0  
Evidence: `screenshots/`

## Audit Scope

Combined UX, visual design, accessibility, release, and share-readiness audit of the published GitHub Pages app. Screenshots were captured from the live public app and saved locally before findings were written.

## Health Summary

- Overall product health: strong
- Live site: built and returning HTTP 200
- JavaScript syntax: passes
- Browser console during export/version checks: no errors
- Export checks: JSON plan, printable binder, and HTML client packet all download
- GitHub state: public repo, homepage URL set, Pages built
- Accessibility structure scan: no missing visible labels, no missing image alt text, small delete controls found

## 10 Audit Passes

1. Overview dashboard  
   Screenshot: `screenshots/01-overview-dashboard.png`  
   Health: strong foundation with clear KPIs and plan health. Risk: the top action bar wraps into two rows at desktop width, making the page feel busier than it needs to.

2. Guest CRM  
   Screenshot: `screenshots/02-guest-crm.png`  
   Health: capable and dense. Risk: guest table fields truncate heavily, especially emails, groups, and meal fields. This makes scanning harder for real guest lists.

3. Budget studio  
   Screenshot: `screenshots/03-budget-studio.png`  
   Health: useful financial surface with chart and editable rows. Risk: table columns clip labels and date placeholder text. The right-side chart is helpful, but the editable table needs more breathing room.

4. Vendor pipeline  
   Screenshot: `screenshots/04-vendor-pipeline.png`  
   Health: strong workflow concept with stage columns and vendor detail. Risk: kanban columns squeeze controls tightly, causing cramped selects, dates, and delete buttons.

5. Timeline and tasks  
   Screenshot: `screenshots/05-timeline-tasks.png`  
   Health: one of the clearest planner workflows. Task priority, owner, due date, dependency, and board state are visible. Risk: dense task cards may need clearer hierarchy once many tasks exist.

6. Wedding-day mode and binder entry  
   Screenshot: `screenshots/06-day-mode-binder.png`  
   Health: excellent day-of command surface. The current moment highlight, alerts, and binder/mobile export buttons are easy to understand. Risk: the lower vendor/contact panels are below the first fold, so mobile crews may need faster jump links.

7. Reports and exports  
   Screenshot: `screenshots/07-reports-exports.png`  
   Health: strong packet/export center. Risk: packet section checkboxes are visually centered away from their labels, which weakens scan clarity and click confidence.

8. About and version panel  
   Screenshot: `screenshots/08-about-version.png`  
   Health: clear version, storage, hosting, and release-link reassurance. Risk: privacy/storage details are good but could link directly to `PRIVACY.md` from the modal.

9. Mobile overview  
   Screenshot: `screenshots/09-mobile-overview.png`  
   Health: responsive layout works and controls remain usable. Risk: the expanded dark navigation consumes most of the first mobile viewport before the user reaches the actual planning workspace.

10. Mobile wedding-day mode  
    Screenshot: `screenshots/10-mobile-day-mode.png`  
    Health: mobile mode starts correctly and key controls remain visible. Risk: the user still has to scroll past a large navigation and topbar stack before seeing the day-of content.

## UX Strengths

- The app feels like a real operations tool, not a landing page.
- Core planner workflows are broad and credible: guests, budget, vendors, timeline, reports, portals, production, and day mode.
- The day-of mode is one of the strongest product surfaces.
- Export options are easy to find and now cover practical handoff formats.
- Version and storage messaging improves trust.

## UX Risks

- The topbar is carrying too many actions at once, especially at desktop widths where it wraps.
- Data-heavy tables are useful but cramped; several values are visibly clipped.
- Vendor pipeline controls compete with the kanban layout.
- Mobile starts with navigation first, content second. This slows urgent day-of use.
- Reports checkbox alignment makes section selection feel less polished.

## Accessibility Risks

- Delete row actions are about `36x26`, below comfortable target height.
- Screenshot evidence suggests good labels and alt text, but full keyboard order and screen-reader announcements still need hands-on testing.
- Dense table inputs may be tiring for keyboard-only users because there are many focus stops per row.
- Mobile navigation is visible and operable, but its height may create extra scrolling burden.

## Verification Notes

- `node --check app.js` passed.
- Public app returned HTTP 200.
- GitHub Pages status was `built`.
- Downloads verified:
  - `vowsuite-wedding-plan.json`
  - `vowsuite-wedding-day-binder.html`
  - `vowsuite-client-packet.html`
- Reset safety verified: restoring demo data opens a backup-first confirmation.
- About panel verified: shows `v1.1.0`.

## Recommended Fix Order

1. Collapse mobile navigation behind a menu or make it horizontally compact.
2. Move lower-priority topbar actions into a compact actions menu.
3. Increase row-action target size to at least 40px high, ideally 44px.
4. Improve table density with wider minimum columns, better horizontal scroll cues, and non-truncated key fields.
5. Rework report checkbox rows so labels and controls are visually connected.
6. Add day-mode jump links for Now, Vendors, Contacts, Alerts, and Checks.
7. Add a direct Privacy link inside the About modal.
8. Run a keyboard-only audit after the layout fixes.

## Evidence Limits

This audit used screenshots, browser checks, export checks, and a lightweight DOM accessibility scan. It does not certify full WCAG compliance. A complete accessibility audit should include keyboard-only traversal, screen-reader testing, focus order review, contrast measurement, and form error-recovery testing.
