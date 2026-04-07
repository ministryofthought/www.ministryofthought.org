# Issues and Enhancements
Date: 2026-04-07

This note records issues encountered and enhancements required.
It follows on from `repository-review-findings.md`, continuing the `Rn`
numbering sequence.

## R6. Search page needs to be more helpful when there is no topic match

Severity: Low

When the user is sent to the search page from the home page, the topic search
box is prepopulated with their search.  If there is no match with the list of
topics, the "Search by major concept / topic" section is empty apart from the
input box.  This is not helpful.  If there is no match for what the user has
entered, there should be some text stating that no matching topics have been
found, and a clickable button or link to let the user do a full-text search
instead.  This should apply whether the user is redirected from the home page
or navigates to the search page to enter their search.

## R7. Section display on video pages

Severity: Low

On the page for a video - e.g. /videos/we-believe-resurrection/ - the sections
of the main text are separated into distinct boxes, with rounded corners. I
don't like the effect - I would rather it looked more continuous, maybe with
horizontal separators like there are between videos in the /recent page.

## R8. Kickers are not helpful

The text in small capitals above titles is not generally adding anything to the
user experience.  It is often a duplicate of the title.  Or it is "video support
page", which is not a user-friendly term.  The CSS seems to refer to this text
as "kickers".  There needs to be a better convention for what goes into these,
or they need to be removed.  Whatever is there should be of help to the reader,
or why would we want it?

## R9. MOC-style topics pages

I would like to be able to manage topics pages like MOCs can be handled in
Obsidian.  I want to be able for some topics to write content for the topic
page, embedding links to the relevant other pages on the site.  Then to have
a list of all pages (the current content) at the end.  Ideally, I would be
able to do what Obsidian can do using note database, etc., which is to have
a list at the end of the page of all the pages for that topic which I haven't
already explicitly linked to in the page text.