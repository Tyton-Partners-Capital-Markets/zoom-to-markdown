# Zoom → Markdown

A browser bookmarklet that exports a Zoom Docs meeting transcript to a clean Markdown file, named after the meeting. Runs entirely client-side — nothing is uploaded.

## Install

Open the [install page](https://tyton-partners-capital-markets.github.io/zoom-to-markdown/) and drag the **Zoom → Markdown** button to your bookmarks bar. (Or use the manual paste option on that page.)

## Use

1. Open a meeting's transcript in Zoom Docs (`docs.zoom.us`).
2. Scroll the transcript once so it fully renders.
3. Click the **Zoom → Markdown** bookmark.
4. A `<meeting title>.md` file downloads.

## How it works

Reads the rendered transcript DOM — speaker from each avatar's `aria-label`, the `HH:MM:SS` timestamp, and the spoken text per turn — and assembles Markdown. The filename is taken from the doc title element (`#docs-title`).

## Notes

- Works in Chrome, Edge, and Safari.
- The bookmarklet must stay **URL-encoded**; a raw version can break on install.
- Exported transcripts are confidential deal material — handle accordingly.
