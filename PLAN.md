# Plan: Add a Projects Section

All changes are made in `docs/index.html` only — inline `<style>`, plain HTML/CSS, no JS, frameworks, build step, or new dependencies.
Projects to add:

1. bilhub.dk – A used-car marketplace for Denmark, built with a friend. I learned how to plan features and test them with real users. Link: https://bilhub.dk
2. AI Expert course – A beginner course about AI tools for Ukrainian learners. I learned how to explain complex tools in simple steps.
3. This website – My About Me site, built with an AI coding agent using AGENTS.md, PLAN.md and Git.

## 1. Gather content first (before editing) — DONE

Decide what each project card will say. For each project, prepare:

- A short title
- 1–2 friendly sentences (what it does + what you learned)
- An optional link (GitHub repo, live demo) — omit the link block if there's nothing to link

**Status: Done.** Content is defined by the three projects listed above (bilhub.dk, AI Expert course, and this website). Each has a title and 1–2 friendly sentences; only bilhub.dk has a link. Use these details when implementing step 5.

## 2. Add the navigation link — DONE

In the `<nav>` block (around lines 56–61), add a new anchor between "Quick Facts" and "Contact":

```html
<a href="#projects">Projects</a>
```

**Status: Done.** Added the Projects link between "Quick Facts" and "Contact" in the `<nav>` block of `docs/index.html`.

## 3. Add a `/* Projects */` CSS section — DONE

Inside the `<style>` block, place a new section after the Facts-related rules (before `/* Contact */`), keeping 2-space indentation and a short comment above the section. Reuse the existing pink palette and `--deep-pink`:

```css
/* Projects */
.projects {
  padding: 70px 0;
}
.projects > h2 {
  color: var(--deep-pink);
  font-size: 36px;
  margin-bottom: 8px;
}
.projects > p {
  color: #73435c;
}
.projects .cards {
  grid-template-columns: repeat(2, 1fr);
}
.project-links {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
  margin-top: 16px;
}
.project-links a {
  color: var(--deep-pink);
  font-weight: 800;
}
```

Reusing `.cards`/`.card` keeps the look consistent with Quick Facts. If any _new_ colours are needed, add them as variables in `:root` (line 9) instead of hard-coding, to avoid widening the known colour-variable gap.

**Status: Done.** Added the `/* Projects */` section in `docs/index.html` before `/* Contact */`, using the file's existing one-line rule style and 2-space indentation. Reused `--deep-pink` and the existing muted text colour; no new colours were introduced.

## 4. Add the mobile rule — DONE

In the existing `@media (max-width: 760px)` block (lines 45–49), add:

```css
.projects .cards {
  grid-template-columns: 1fr;
}
```

So project cards stack on small screens, matching the Quick Facts behaviour.

**Status: Done.** Added `.projects .cards { grid-template-columns: 1fr; }` inside the existing `@media (max-width: 760px)` block.

## 5. Add the HTML section — DONE

Insert a new `<section>` between the `#facts` section and the `#contact` section (after line 95):

```html
<section class="projects" id="projects">
  <div class="container">
    <h2>Projects</h2>
    <p>A few things I've built while learning.</p>
    <div class="cards">
      <article class="card">
        <h3>Project name</h3>
        <p>
          One or two friendly sentences about what it does and what you learned.
        </p>
        <div class="project-links">
          <a href="LINK">View project</a>
        </div>
      </article>
      <!-- repeat <article class="card"> for each project -->
    </div>
  </div>
</section>
```

Use `id="projects"` to match the nav anchor, and simple, friendly English throughout.

**Status: Done.** Added the `<section class="projects" id="projects">` between Quick Facts and Contact with all three cards from step 1: bilhub.dk (with a "View project" link to https://bilhub.dk), AI Expert course, and This website. The two projects without links have no link block.

## 6. Verify in a browser

There is no build or test tooling, so verification is manual:

1. Open `docs/index.html` directly in a browser.
2. Click the **Projects** nav link — it should scroll to the new section.
3. Check desktop and a narrow width (~375 px) — cards should go from 2 columns to 1.
4. Check any project links open correctly and text is readable against the pink background (contrast).

## 7. Commit only after approval

Per the working rules, ask before committing — commits on `main` publish straight to the live site. Show the final diff first.

## Progress notes

- Steps 1–5 are complete. The only site file changed is `docs/index.html` (plus this plan file).
- The new CSS follows the surrounding single-line rule style, uses kebab-case class names, and introduces no new colours.
- All three project cards use the content listed at the top of this plan; only bilhub.dk has an external link.
- Step 6 (browser verification) has not been done yet, and step 7 (commit) still requires your approval.

---

**Heads-up (separate from this plan):** `AGENTS.md` says not to add personal data like phone numbers, but the current page has a phone number in both the contact box and footer. This is not part of the Projects work; flagging it in case it should be handled later.
