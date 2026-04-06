# Ministry of Thought — Hugo starter repository

A lightweight Hugo starter repository for an offline-first writing workflow with deployment to Azure Static Web Apps.

## What this starter includes

- Hugo site with no external theme dependency
- Content types for `articles`, `talks`, and standalone `pages`
- Basic tags and series taxonomies
- Simple responsive layout and typography
- Azure Static Web Apps workflow that builds Hugo and uploads the generated `public/` folder
- Portable structure that can later move to Cloudflare Pages with minimal changes

## Working style

Suggested workflow:

- Draft and think in Obsidian or your preferred Markdown notes tool
- Move or copy publishable content into this repository
- Use VS Code for front matter, templates, Git, and local preview

## Local prerequisites

Install Hugo Extended:

- Windows: use `winget install Hugo.Hugo.Extended`
- macOS: use `brew install hugo`
- Other platforms: see Hugo installation docs

## Run locally

```bash
hugo server -D
```

Open the local address printed by Hugo.

## Build locally

```bash
hugo
```

Generated site output will be written to `public/`.

## Azure Static Web Apps

This repo includes a GitHub Actions workflow that:

- installs Hugo Extended
- builds the site
- uploads the generated `public/` directory to Azure Static Web Apps

This means you can keep your existing Azure Static Web App and custom DNS. The main change is that Azure must now deploy the built output rather than serving the repository root directly.

## Key folders

```text
.github/workflows/   Deployment workflow
archetypes/          New-content templates
assets/css/          Site styles
content/             Markdown content
layouts/             Hugo templates and partials
static/              Files copied as-is to the built site
```

## Adding content

Create new content with Hugo:

```bash
hugo new articles/my-new-article.md
hugo new talks/my-new-talk.md
```

Or create files manually inside `content/`.

## Content conventions

### Articles

Stored in `content/articles/`.

Suggested front matter fields:

- `title`
- `date`
- `draft`
- `summary`
- `tags`
- `series`
- `slug`

### Talks

Stored in `content/talks/`.

Suggested additional fields:

- `event`
- `location`
- `talk_date`
- `resources`

### Standalone pages

Stored in `content/pages/`.

For pages like About, Contact, or project information.

## Future migration to Cloudflare Pages

This starter is deliberately host-agnostic:

- content is plain Markdown
- templates are standard Hugo templates
- there is no Azure-specific logic in the site itself

If you move later, the main change should be deployment configuration and DNS.
