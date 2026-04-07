# AI Context for Ministry of Thought

## Purpose of this repository

This repository contains the source for the **Ministry of Thought** website.

The site is a **personal, non-commercial publishing project**. Its purpose is to present thoughtful long-form content clearly and durably, in a way that is easy to maintain over time.

This is **not** a marketing site, growth site, or SEO-driven content business. The audience is expected to be relatively small and selective. The priority is not maximum reach, but a calm, clear, trustworthy presentation of content.

## Product principles

When making changes, optimise for the following:

1. **Clarity**
   - Content should be easy to read and navigate.
   - Visual and interaction design should feel calm, simple, and unobtrusive.
   - Avoid clutter, gimmicks, or visually noisy features.

2. **Maintainability**
   - Prefer simple solutions over clever ones.
   - The site should remain understandable by a human maintainer who did not write the original code.
   - Avoid unnecessary abstractions.

3. **Durability**
   - Favour open, future-proof formats and patterns.
   - Prefer approaches that will continue to work with minimal ongoing maintenance.
   - Generated output should remain simple HTML/CSS/JS where possible.

4. **Low operational overhead**
   - Do not introduce features that create significant moderation, administration, or support burden.
   - Avoid changes that make deployment, debugging, or content authoring significantly more complex.

5. **Restraint**
   - This site should feel intentional and thoughtful, not over-engineered.
   - Add only what is needed.
   - Default to doing less, but doing it well.

## Intended audience and usage

The site is mainly for people who intentionally choose to engage with the content. It is not designed around public virality or broad anonymous engagement.

The owner does **not** want to spend significant time on:
- marketing
- SEO optimisation for its own sake
- comment moderation
- managing complex community features

Private or approval-based interaction features may be acceptable in future, but only if they remain simple and low-maintenance.

## Technical context

Current preferred stack:

- **Hugo** for static site generation
- Content authored in **Markdown**
- Hosted as a **static site in Azure**
- Source controlled in **GitHub**
- Existing deployment flow already in place via GitHub Actions / Azure Static Web Apps

Assume this stack is preferred unless there is a very strong reason to change it.

## Technical preferences

When proposing or making changes:

- Prefer **Hugo-native solutions** over adding custom application logic
- Prefer **static-site-friendly** approaches
- Prefer **simple HTML/CSS** over unnecessary JavaScript
- Use JavaScript only where it brings clear user value and there is no simpler alternative
- Avoid introducing large frameworks or build complexity unless explicitly requested
- Avoid unnecessary third-party services
- Avoid unnecessary dependencies

## Deployment and operational constraints

Changes should preserve or respect the existing deployment model.

Important:
- Do not make changes that are likely to break Azure static site deployment
- Do not assume server-side runtime capability beyond what a static site normally has
- Do not introduce features requiring a persistent backend unless explicitly requested
- Keep configuration straightforward and transparent

## Coding style preferences

- Keep code readable and unsurprising
- Prefer explicitness over cleverness
- Keep file and template structure simple
- Make the minimum necessary change for a task
- Do not refactor unrelated areas unless there is a strong justification
- Preserve existing conventions where reasonable
- Comment sparingly, but clearly where logic is non-obvious

## UX and design guidance

The site should feel:
- calm
- thoughtful
- clear
- credible
- quietly distinctive

It should **not** feel:
- flashy
- sales-driven
- trendy for its own sake
- overloaded with animations or effects

When making design decisions:
- prioritise readability
- prioritise navigation clarity
- preserve good contrast and accessibility
- avoid decorative UI that competes with the content

## Accessibility expectations

Even if full formal compliance is not the main goal, changes should follow good accessibility practice where practical:

- sufficient colour contrast
- visible focus states
- usable keyboard navigation
- semantic HTML
- avoid relying solely on colour to communicate meaning
- responsive behaviour that works cleanly on mobile and desktop

## Search and discoverability

Search and navigation should help users reach content efficiently, but this site is not intended to become an aggressively optimised SEO machine.

When working on search or metadata:
- support sensible discoverability
- avoid spammy or over-optimised patterns
- prefer accuracy and usefulness over growth tactics

## Content model principles

Content should remain portable and easy to edit.

Prefer:
- Markdown content
- front matter that is understandable and not overcomplicated
- clear Hugo archetypes, layouts, and partials
- structures that support long-term content maintenance

Avoid:
- locking important content into fragile custom formats
- over-complex front matter schemas unless clearly necessary

## Approach to AI-generated changes

When making changes in this repository:

- Check that the current branch name starts with `ai/`.  If not, ask for
  confirmation before proceeding to make any changes.
- Work on the current branch only
- Keep changes scoped to the task
- Explain what you changed and why
- Highlight any assumptions
- Flag any risks or follow-up checks
- Prefer small, reviewable diffs
- Do not silently introduce broad architectural changes

If a request is ambiguous, prefer the interpretation that:
- keeps the implementation simplest
- preserves maintainability
- avoids adding dependencies
- stays closest to the existing site philosophy

## Things to avoid unless explicitly requested

Do not introduce any of the following unless specifically asked:

- JavaScript frameworks
- heavy client-side applications
- complex CMS integrations
- analytics-heavy tooling
- SEO growth tactics
- public commenting systems
- chat widgets
- large visual redesigns
- backend services for features that can be handled statically
- unnecessary package dependencies
- complex build pipeline changes

## Preferred decision heuristic

When choosing between options, generally prefer the one that is:

1. simpler
2. easier to maintain
3. more compatible with Hugo and static hosting
4. easier to understand later
5. less dependent on third parties
6. more aligned with the calm, content-first purpose of the site

## Repository-specific working style

Before making changes:
- inspect the relevant layouts, partials, assets, and config
- understand the existing pattern before editing
- avoid changing unrelated files

After making changes:
- summarise the files changed
- summarise the reasoning
- identify anything that should be manually tested
- identify any likely mobile/responsive implications if relevant

## In case of doubt

If uncertain, default to:
- preserving the existing architecture
- making the smallest effective change
- favouring clarity over cleverness
- asking for less complexity, not more