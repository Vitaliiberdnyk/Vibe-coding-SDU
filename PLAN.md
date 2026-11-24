# Plan: Contact section and WCAG AA colours

All site changes are in `docs/index.html` only — inline `<style>`, plain HTML/CSS, no JS, frameworks, build step, or new dependencies.

## Shared decisions

- Work happens in **two passes**: contact first, colours second.
- Each pass ends with a review gate: show the diff plus browser screenshots at 1280px and 375px (and a contrast-ratio table for Pass 2), then stop for explicit "commit it" approval.
- Approved passes are committed **locally on `main` only**. No push. After both commits, push them together on a single separate instruction.
- Project section is already implemented and is **out of scope** for this round.
- Keep friendly English, the pink theme, kebab-case classes, 2-space indentation, and short CSS section comments.
- No phone number or physical address anywhere. Email stays as placeholder `hello@example.com` for now.

## Pass 1 — Contact (start here)

1. Remove the phone link from the contact box and footer; delete the `.phone` CSS rule.
2. In the contact box, replace `.email` / `.phone` with one shared `.contact-link` class and show three labelled links in this order:
   1. `Email` — `mailto:hello@example.com`
   2. `LinkedIn` — `https://www.linkedin.com/in/vitaliiberdnyk/`
   3. `GitHub` — `https://github.com/Vitaliiberdnyk`
3. External profile links use `target="_blank" rel="noopener noreferrer"`.
4. Replace the contact note with: "Email is a placeholder for now. You can also find me on LinkedIn and GitHub."
5. Footer mirrors the same three links in the same order, replacing the current email + phone pair.
6. Update `AGENTS.md` in this pass:
   - LinkedIn and GitHub links are allowed; phone and physical address remain forbidden.
   - Email is intentionally still a placeholder.
   - Clarify that publishing happens on **push**, not on a local commit.
   - Record that local commits on `main` are made only after approval and are not pushed until separately instructed.
7. Verify in a browser at 1280px and 375px. Show the diff and screenshots, then wait for approval.
8. After approval, make a local commit titled: **"Update contact section with LinkedIn and GitHub"**.
9. Stop completely. Wait for a fresh go-ahead before starting Pass 2.

## Pass 2 — Colours

1. Introduce semantic `:root` variables for every colour, including rgba shadows and hover states — for example `--page-bg`, `--text`, `--pink-deep`, `--pink-bright`, `--accent`, `--surface`, `--border`, `--shadow-soft`.
2. Replace all hard-coded hex, `white`, and rgba values, including the repeated `#851247`.
3. Header background becomes `#b51661`; white logo/nav text then measures 6.46:1.
4. Hero accent becomes `#d11a75`; 4.66:1 on the page background.
5. Card and contact-box boundaries get a 3:1+ border token (`#d11a75` is 5.10:1 on white; `--pink-deep` is 7.52:1 on the pale contact background). Pale section backgrounds stay.
6. Every text pair reaches at least 4.5:1. No large-text exception is relied on.
7. Verify the whole page at 1280px and 375px, including the contact section now using variables. Show the diff, screenshots, and a before/after contrast table, then wait for approval.
8. After approval, make a local commit titled: **"Migrate colours to variables and fix WCAG AA contrast"**.
9. Still no push. Wait for one instruction, then push both commits together.

## Out of scope

- Projects section content and layout.
- Replacing the placeholder email with a real address.
- Any phone number or physical address.
- Adding new CSS/JS files or any build tooling.
