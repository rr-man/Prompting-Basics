# Changelog

All notable changes to **The Prompt Brief** (COEO AI Enablement) are documented here.
This project follows [Semantic Versioning](https://semver.org/): MAJOR.MINOR.PATCH.

- **MAJOR** — large restructures or breaking changes to the tool's layout/flow
- **MINOR** — new sections, tabs, or features
- **PATCH** — copy edits, styling tweaks, small fixes

The version number is recorded in three places on every release: the HTML header comment,
the visible footer tag, and this file.

---

## [1.8.0] — 2026-07-09

### Changed
- Redesigned the internal video library on the Video Tutorials tab into a **two-column layout**: a list of all videos on the left, with the selected video playing on the right (replacing the top tab strip).

---

## [1.7.1] — 2026-07-09

### Added
- Added **Copilot for Executives** as the sixth video in the internal Vimeo video library.

---

## [1.7.0] — 2026-07-09

### Added
- Added **Executive Leadership** as a seventh department, appearing in both the "Vague in, clear out" examples (Basic Prompting) and the "By department" defaults (Build a prompt).
- Expanded every "By department" team in Build a prompt to **4 samples each** (7 departments x 4).
- Expanded every app in the Library (Basic Prompting) to **4 examples each** (Copilot Chat, Outlook, Word, Excel, PowerPoint, Teams).
- Added **Copilot for IT** as the fifth video in the internal Vimeo video library.
- Added a floating **"Copied to clipboard" toast** notification for all copy actions.

### Fixed
- Corrected the "Common Mistakes" heading from "Five habits to drop" to **"Six habits to drop"** to match the six examples shown.
- Fixed a page-jump bug where clicking **Copy** scrolled the page to the bottom; the clipboard fallback now uses `preventScroll` and a pinned off-screen textarea.

### Changed
- Updated the "By department" toggle badge to read **7 teams**.

---

## [1.6.0] — 2026-07-09

### Added
- Introduced the **internal Vimeo video library** on the Video Tutorials tab with a tab selector — only the selected video loads at a time (Operations, Finance, Sales, Copilot & Agents).
- Added a **"Next" navigation button** at the bottom of Basic Prompting, Advanced Prompting, and Video Tutorials to move through the tabs in order.
- Added the **"Created by Ron Mangune"** credit with LinkedIn link in the footer (lower left).

### Changed
- Moved the **"Vague in, clear out"** section out of the hero to sit as its own section (02), between The Framework and The Library.
- Renamed the program branding to **COEO AI Enablement** across the top bar and footer.
- Made the COEO banner a **consistent content-width letterhead** (capped at page width) instead of full-bleed.
- Restyled the "Browse training events" callout button to the **gold theme** for consistency.

### Removed
- Removed the SharePoint "MS 365 Copilot and Agents" link-out card (now covered by the inline Vimeo library).

---

## [1.5.0] — 2026-07-09

### Added
- Added a **table of contents** to both Basic Prompting and Advanced Prompting, with anchor links and sticky-header clearance.
- Added department-specific **"Vague in, clear out"** examples with a team selector (Support, Account Management, Sales, Finance, Project Management, Engineering).
- Added a **"Live training" callout** linking to Microsoft's Copilot training events.
- Added a **featured video card** (Microsoft's "Get better Copilot responses with great prompting") to the top of the Video Tutorials tab.

### Changed
- Promoted the "Vague in, clear out" label to a full section heading with gold highlight for visibility.

---

## [1.4.0] — 2026-07-09

### Added
- Added the **Video Tutorials** tab as a standalone top-level tab, sectioned per application (Word, Excel, PowerPoint, Outlook, Teams), each linking to Microsoft's official demos.

### Changed
- Widened the tab bar to fit four tabs evenly.

---

## [1.3.0] — 2026-07-09

### Added
- Wired the Library **"Copy"** and **"Use in builder"** buttons so a card can load its four blocks directly into the Build a prompt tab, auto-selecting the matching app.
- Added a **"Start from scratch" confirmation modal** (custom, iframe-safe) that only appears when the builder has unsaved content.

### Changed
- Decomposed all Library and department prompts into discrete Goal / Context / Expectations / Source fields.

---

## [1.2.0] — 2026-07-09

### Added
- Added the **Advanced Prompting** tab: seven Microsoft-sourced techniques, each with editable, default-filled snippets that fold into the builder's Expectations.
- Added an inline **"Show advanced prompting techniques"** toggle inside the Build a prompt tab.

---

## [1.1.0] — 2026-07-09

### Added
- Added the **Build a prompt** tab: an interactive four-block builder with product picker, tone/format chips, live output, and a strength meter.
- Added the **"By department"** starting mode with role-based sample prompts.

---

## [1.0.0] — 2026-07-09

### Added
- Initial release: **Basic Prompting** tab with the four-block framework (Goal, Context, Expectations, Source), the "Vague in, clear out" comparison, the Library of ready-to-use prompts by app, and Common Mistakes.
- COEO-branded single-file HTML, deployable to GitHub Pages and embeddable in Confluence via iframe.

---

_Dates reflect when entries were catalogued. Earlier 1.x versions were reconstructed retroactively when versioning was introduced in 1.7.0; adjust dates to match your commit history as needed._
