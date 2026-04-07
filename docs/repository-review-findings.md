# Repository Review Findings

Date: 2026-04-07
Branch reviewed: `ai/feature-enhancements`

This note records the main flaws identified during a repository scan so they can
be discussed and fixed in later sessions.

The numbering below is intended to stay stable, so we can refer to items as
`R1`, `R2`, and so on.

## R1. Homepage search does not carry the query through to results

Severity: High

The homepage includes a search form that submits a `q` query parameter to the
search page. However, the search page does not read that value or use it to
prefill or filter the topic list.

In practice, this means a visitor can type a search on the homepage, press the
button, and then land on the search page without seeing their query reflected in
the interface. The primary call to action appears to work, but it does not
complete the search flow.

Why this matters:

- It creates a misleading user experience.
- It makes the main search entry point feel broken.
- It weakens confidence in the site even though the build succeeds.

Relevant files:

- `layouts/index.html`
- `layouts/search/list.html`

## R2. Markdown is configured to allow raw HTML globally

Severity: High

The Hugo configuration enables Goldmark's `unsafe` mode globally. That allows
raw HTML in Markdown content across the site.

This is especially risky in a repository that may later use AI-assisted content
workflows. A malformed or unsafe HTML snippet in Markdown could introduce
unwanted embeds, layout breakage, or cross-site scripting behaviour into the
generated output.

Why this matters:

- It broadens the site’s content-safety risk surface.
- It increases the chance that future content automation could publish unsafe
  markup.
- It is a wide-reaching setting rather than a narrowly scoped exception.

Relevant files:

- `hugo.toml`

## R3. Taxonomy page shows the wrong "related" taxonomy for series

Severity: Medium

The taxonomy template labels the secondary panel as "Related {{ taxonomy }}",
but the implementation always pulls chips from the `topics` taxonomy.

That means a series page can show a heading such as "Related series" while
actually listing topics. The page still renders, but the content is misleading
and semantically inconsistent.

Why this matters:

- It gives incorrect contextual navigation.
- It makes the taxonomy template less reusable than it appears.
- It could confuse readers trying to browse by series.

Relevant files:

- `layouts/taxonomy/taxonomy.html`

## R4. Several user-facing strings contain broken character encoding

Severity: Medium

There are multiple visible strings in templates and documentation that appear to
have mojibake, for example:

- `Â·` where a middle dot should appear
- `â˜°` where the mobile menu icon should appear
- `â€¦` where an ellipsis should appear
- `â†’` where a right arrow should appear

These are not just source-formatting issues. They would be shown directly to
site visitors in titles, labels, placeholders, and navigation text.

Why this matters:

- It visibly reduces quality and credibility.
- It makes key navigation elements look broken.
- It suggests there may be text encoding inconsistencies in the editing
  workflow.

Relevant files:

- `layouts/partials/head.html`
- `layouts/partials/header.html`
- `layouts/partials/footer.html`
- `layouts/index.html`
- `README.md`

## R5. Mobile navigation depends too heavily on JavaScript and lacks state

Severity: Medium

On narrow screens, the primary navigation is hidden by CSS until JavaScript adds
an `open` class. If JavaScript fails or is disabled, navigation becomes
unavailable on mobile-sized layouts.

The toggle button also does not expose expanded/collapsed state via
accessibility attributes such as `aria-expanded`.

Why this matters:

- It creates a progressive-enhancement failure for a core navigation path.
- It makes the site less robust than a static Hugo site should ideally be.
- It weakens accessibility for keyboard and assistive-technology users.

Relevant files:

- `layouts/partials/header.html`
- `layouts/partials/footer.html`
- `assets/css/site.css`

## Notes

- The site built successfully with `hugo` during this review.
- No immediate deployment-breaking template errors were found.
- The main concerns are functional correctness, safety defaults, semantics, and
  accessibility.
