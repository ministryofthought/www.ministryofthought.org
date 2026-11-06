# Placeholder content inventory

Recorded: 2026-11-06
Baseline commit: `6af6c67eedd13ba5426c511443b469b5cc9af2b6`

The owner identified the current publishing content as placeholders and plans
to add real content alongside it before requesting cleanup. This inventory
records all 14 files currently under `content/`. Nothing should be removed
until that cleanup is requested.

## Placeholder items for future removal

| Path | Title |
| --- | --- |
| `content/articles/community-as-practice.md` | Community as Practice |
| `content/articles/why-doctrine-matters.md` | Why Doctrine Matters |
| `content/videos/for-the-love-of-friends.md` | For the Love of: Friends |
| `content/videos/vision-community-life.md` | Vision Series: Community Life |
| `content/videos/we-believe-one-god.md` | We Believe: One God |
| `content/videos/we-believe-resurrection.md` | We Believe: The Resurrection |
| `content/series/for-the-love-of/_index.md` | For the Love Of |

The individual series introduction is a placeholder item, unlike the top-level
Series directory page. If real content subsequently uses this series, retain
the series page and revise its placeholder introduction instead of deleting it.

## Singleton and section pages to retain

Keep these pages during placeholder cleanup, including when their copy is
revised:

| Path | Title |
| --- | --- |
| `content/about/_index.md` | About |
| `content/articles/_index.md` | Articles |
| `content/recent/_index.md` | Recent content |
| `content/search/_index.md` | Search |
| `content/series/_index.md` | Series |
| `content/topics/_index.md` | Topics |
| `content/videos/_index.md` | Videos |

## Instructions for future cleanup

When the owner asks to remove the placeholder content:

1. Use the seven explicit placeholder paths above as the starting list. Do not
   delete whole sections or identify placeholders solely by date, title,
   taxonomy membership, or the presence of an `_index.md` filename.
2. Compare each remaining candidate with its version at the baseline commit.
   If a page has become real content, preserve it. If edits make its status
   unclear, resolve that uncertainty before deleting it. Follow renames through
   Git history where necessary; do not assume a reused path is still disposable.
3. Preserve new content added after this inventory and all retained pages above.
   Shared topics and series may be used by real content; do not remove them
   indiscriminately. Hugo-generated taxonomy pages need no source-file deletion.
4. Check for links to removed pages and update any affected navigation or
   editorial references without deleting real content. Run the Hugo build to
   check the resulting site.
5. Update this record with the cleanup outcome, including items retained because
   they were replaced with real content or are still needed by real content.

This inventory is a historical baseline. Do not automatically add future content
to the placeholder list.
