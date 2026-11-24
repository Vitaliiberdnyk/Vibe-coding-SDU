# Project

Personal "About Me" site for Vitalii Berdnyk. Single static page, plain HTML/CSS only — no JS, frameworks, build step, or dependencies.

- GitHub Pages serves the `docs/` folder from the `main` branch; the entire site is `docs/index.html` (inline `<style>`, no separate CSS/JS files).
- No package manifest, CI, or test/lint tooling exists. Verify changes by opening `docs/index.html` in a browser; there are no developer commands to run.

## Working rules

- Ask before committing, pushing, or deleting/renaming files. Commits on `main` are local; publishing to the live site happens on push to `main`. Approved passes are committed locally only, and are not pushed until separately instructed.
- Never add a phone number or physical address to the site. Contact uses placeholder `hello@example.com` for now, alongside LinkedIn and GitHub profile links.
- Keep visible text in simple, friendly English.

## HTML/CSS conventions

- Class names: kebab-case. Indentation: 2 spaces. Short comment above each CSS section.
- Preserve the pink theme. Reuse the `--deep-pink` variable in `:root` where one exists.
- All colours are defined as CSS variables in `:root`; no colour values are hard-coded elsewhere in `docs/index.html`. Text contrast meets WCAG AA (≥ 4.5:1 for normal text).

## Next steps (current)

1. Contact pass — done and committed locally as `5f9ea72` ("Update contact section with LinkedIn and GitHub").
2. Colour pass — implemented in `docs/index.html`; awaiting review and local commit. No push.
3. Projects section — already implemented; out of scope for this round.
4. Push both local commits together only after a separate instruction.

