# Handoff Note

## Project

Personal "About Me" site for Vitalii Berdnyk. Plain HTML/CSS, no frameworks. GitHub Pages serves the `docs/` folder; the site lives in `docs/index.html`.

## History (from git log)

| Commit | Date | What changed |
| --- | --- | --- |
| `b2807ab` | 2026-10-06 | Initial "test" commit adding `Readme.md`. |
| `9cacb60` | 2026-10-06 | "Web site" — added `index.html` (~114 lines) with the full one-page layout. |
| `b10deae` | 2026-10-06 | Moved `index.html` into `docs/` for GitHub Pages. |
| `8415652` | 2026-11-10 | Added `AGENTS.md` with project conventions and rules. |
| `f8a3cf3` | 2026-11-10 | Darkened nav hover colour. |
| `398ec13` | 2026-11-17 | Replaced phone number with placeholder email; added colour rule to `AGENTS.md`. |

All commits are by Vitaliiberdnyk. Working tree is clean; nothing is staged or pushed.

## Current state

One page with a header/nav, hero, "Quick Facts" cards, contact box, and footer. Contact details are placeholders (`hello@example.com`). The site is intentionally pink-themed.

## Next steps

1. Fix colour contrast to meet WCAG AA (4.5:1); note that `AGENTS.md` requires colours as CSS variables in `:root`, but most colours in `docs/index.html` are still hard-coded.
2. Replace placeholder contact details with real links (no phone or address on the site).
3. Add a projects section.
4. Ask before committing, pushing, or deleting/renaming files.
