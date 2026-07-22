# Zoom → Markdown

A browser bookmarklet that exports a Zoom Docs meeting transcript to a clean Markdown file, named after the meeting, and copies the same Markdown to your clipboard. Runs entirely client-side — nothing is uploaded.

## Install

Open the [install page](https://tyton-partners-capital-markets.github.io/zoom-to-markdown/) and drag the **Zoom → Markdown** button to your bookmarks bar. (Or use the manual paste option on that page.)

## Use

1. Open a meeting's transcript in Zoom Docs (`docs.zoom.us`).
2. Click the **Zoom → Markdown** bookmark.
3. A `<meeting title>.md` file downloads, and the same Markdown is copied to your clipboard.

## How it works

Reads the rendered transcript DOM — for each turn it pulls the speaker name, the timestamp, and the spoken text — and assembles Markdown. The filename is taken from the doc title element (`#docs-title`), falling back to the page title.

Zoom's transcript UI uses styled-component class names (e.g. `.sc-hEvKXk.goBswG`), which are regenerated on Zoom deploys — so a Zoom update can change the classes and stop the export from finding turns. If that happens, inspect the transcript panel's DOM and update the selectors in `index.html` (both the drag button and the manual-paste textarea, kept in sync), then re-URL-encode.

## Notes

- Works in Chrome, Edge, and Safari.
- The bookmarklet must stay **URL-encoded**; a raw version can break on install.
- Exported transcripts are confidential deal material — handle accordingly.
