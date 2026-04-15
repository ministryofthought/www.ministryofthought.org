# Ministry of Thought Hugo starter

This is a custom Hugo starter site implementing the wireframe direction discussed in chat:

- compact, content-first layout
- videos and articles as the primary content types
- topic pages for conceptual browsing
- series pages for curated pathways
- recent content page
- dual search model: concept/topic search on-site and Google full-text search

## Run locally

```bash
hugo server
```

## Key sections

- `content/videos/` — video pages
- `content/articles/` — article pages
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

## Bible references

Use the `bible` shortcode for inline passage links:

```markdown
{{< bible "John 3:16" >}}
```

Use the paired `biblequote` shortcode for quoted passages:

```markdown
{{< biblequote ref="John 3:16" >}}
For God so loved the world...
{{< /biblequote >}}
```

Both shortcodes use the default Bible version and passage URL configured in `hugo.toml`.

## YouTube embeds

Video pages can embed either a single YouTube video:

```toml
youtube = "VIDEO_ID"
```

or a YouTube playlist:

```toml
youtubePlaylist = "PLAYLIST_ID"
```

If both are present, the single video is used.

## Next likely step

After the IA is agreed, the content model can be formalised and the templates can be adapted to the final metadata structure and automation workflow.

## AI Guidance

If you are an AI agent working on this repository, you must read:

docs/ai-context.md
