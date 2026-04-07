# Ministry of Thought Hugo starter

This is a custom Hugo starter site implementing the wireframe direction discussed in chat:

- compact, content-first layout
- video support pages as the primary content type
- topic pages for conceptual browsing
- series pages for curated pathways
- recent videos page
- dual search model: concept/topic search on-site and Google full-text search

## Run locally

```bash
hugo server
```

## Key sections

- `content/videos/` — video support pages
- `content/topics/` — taxonomy landing page
- `content/series/` — taxonomy landing page
- `content/search/` — search page
- `content/about/` — about page
- `content/recent/` — chronological browse page

## Current sample data

The sample pages use Woodside Church videos as placeholder embeds, so the layout can be tested with real YouTube content while the information architecture is still being refined.

## Notes

- The visual style is intentionally restrained.
- The burger menu appears on narrow screens.
- The search page includes a small client-side topic search built from Hugo taxonomies.
- The full-text search button sends the user to Google with a `site:ministryofthought.org` query.

## Next likely step

After the IA is agreed, the content model can be formalised and the templates can be adapted to the final metadata structure and automation workflow.

## AI Guidance

If you are an AI agent working on this repository, you must read:

docs/ai-context.md