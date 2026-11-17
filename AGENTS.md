# Project

Personal "About Me" site for Vitalii Berdnyk. Single static page, plain HTML/CSS only — no JS, frameworks, build step, or dependencies.

- GitHub Pages serves the `docs/` folder from the `main` branch; the entire site is `docs/index.html` (inline `<style>`, no separate CSS/JS files).
- No package manifest, CI, or test/lint tooling exists. Verify changes by opening `docs/index.html` in a browser; there are no developer commands to run.

## Working rules

- Ask before committing, pushing, or deleting/renaming files. Commits on `main` publish directly to the live site.
- Never add personal data (phone number, physical address) to the site. Contact uses placeholder `hello@example.com` in two places (contact box + footer).
- Keep visible text in simple, friendly English.

## HTML/CSS conventions

- Class names: kebab-case. Indentation: 2 spaces. Short comment above each CSS section.
- Preserve the pink theme. Reuse the `--deep-pink` variable in `:root` where one exists.
- **Known gap:** the `AGENTS.md` rule "all colours as CSS variables in `:root`, never hard-coded" is NOT met — most colours in `docs/index.html` are still hard-coded hex/rgba values. Fixing colour contrast (WCAG AA ≥ 4.5:1) is a pending task; expect to convert these to variables as part of that work rather than assuming the rule is already followed.

## Next steps (from repo handoff)

1. Fix colour contrast to WCAG AA and migrate hard-coded colours to `:root` variables.
2. Replace placeholder contact email with real contact links (still no phone/address).
3. Add a projects section.

