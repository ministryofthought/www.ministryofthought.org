# Ministry of Thought Hugo starter

This is a custom Hugo starter site implementing the wireframe direction discussed in chat:

- compact, content-first layout
- videos and articles as the primary content types
- reusable external resource records, including books and reviews
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

## Resources

Resources live under `content/resources/` and appear in the Resources menu,
Recent content, related content, and their assigned topics. The Resources
directory is alphabetical; Recent uses the date the record was added, not the
book's publication year. These are real content records, outside the historical
placeholder inventory in `docs/placeholder-content.md`.

Create a record with:

```bash
hugo new content resources/my-book/index.md
```

The `resources` archetype includes optional bibliographic fields, cover metadata,
and repeatable `onlineLinks` and `purchaseLinks` tables. Fill in the relevant
fields, remove unused link tables, and set `draft = false` to publish. Use
`resourceKind` for Book, Website, Article, or another suitable description.
Publication years belong in `bibliography.year`; `date` is the resource record's
site date. For a website, omit book-specific fields and include its address in
`onlineLinks`; access dates can be recorded in the link's `note`.

Put a cover alongside `index.md` and set `cover.src` to its filename. Supply
descriptive `alt` text and the image's credit and source. The example record is
`content/resources/motyer-2016-psalms-by-the-day/index.md`.

Write descriptions and optional `## Review` sections in the Markdown body.
Each link table has a `label`, `url`, and optional `note`. Use notes to distinguish
samples, free full texts, and paid digital access; multiple shops are supported.

Reuse a resource in any page's references without duplicating its details:

```markdown
{{< resource "motyer-2016-psalms-by-the-day" >}}
{{< resource ref="motyer-2016-psalms-by-the-day" pages="312–314" >}}
{{< resource ref="motyer-2016-psalms-by-the-day" label="Motyer's Psalms commentary" >}}
```

By default the shortcode renders a linked citation with author, year, title,
subtitle, and edition when supplied. Publisher and place are shown on the
resource page only. `label` overrides the link text; `pages` adds a reference-specific page
range. The build fails for an unknown resource, helping catch broken references.
Keep the resource's path stable once it is referenced.

The resource page displays bibliographic properties individually, with title and
subtitle combined in its Title field. Its Related content section automatically
lists published pages whose rendered content links to the resource, including
`resource` shortcodes and ordinary internal Markdown links. Each referring page
appears once; pages sharing only a topic are not included. Draft and future pages
appear only when enabled in the Hugo build.

## AI Guidance

If you are an AI agent working on this repository, you must read:

docs/ai-context.md
