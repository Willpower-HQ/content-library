# Willpower Media Archive

Every Willpower panel, recorded and unpacked. This repo holds the media archive page and
the written breakdowns behind each session.

**Repo:** https://github.com/Willpower-HQ/content-library

## Live site

Not deployed yet from this repo. Connect Netlify once and every push to `main` publishes
automatically:

> **Deploy:** https://app.netlify.com/start/deploy?repository=https://github.com/Willpower-HQ/content-library

`netlify.toml` is already set up (publish directory `.`, no build step), so accept the
defaults. After the first deploy, put the real URL here:

> **Live:** _(paste your Netlify URL after the first deploy)_

Note: the old `willpower-media-draft.netlify.app` is Bill's separate site. It has not been
updated since June and does not contain any of this work. Ignore it.

## What is in here

| Path | What it is |
| --- | --- |
| `index.html` | The archive page. Card grid, series legend, links into every breakdown. |
| `articles/` | The written breakdowns, one file per session. |
| `list-version.html` | Earlier list layout, kept for reference. Not linked from anywhere. |
| `bill-version.html` | June 11 snapshot of the accordion layout, before it was flattened. |
| `media.html` | Another early layout. Reference only. |
| `world-of-sports-2026.html` | Standalone World of Sports page. |
| `panel-*.html` | Standalone per-panel pages with their own `panel.css`. |
| `WH Thumbnails/` | Event photography. |
| `voice/about-bill.md` | The writing voice. Read it before drafting any copy. |

## Editing

Work in the browser with no setup by pressing `.` on the repo page, or go to
https://github.dev/Willpower-HQ/content-library

Or locally:

```bash
git clone https://github.com/Willpower-HQ/content-library.git
cd content-library
claude
```

Then commit and push. If Netlify is connected, that publishes it.

## House rules

Read `AGENTS.md` before writing any copy. The two that get broken most:

1. **No em dashes.** Anywhere. Use periods, commas, or parentheses.
2. **Article headlines wrap to exactly three lines.** The headline column is 800px at 52px,
   so three lines is roughly 80 to 95 characters. Check how it actually wraps before
   calling it done.

Every takeaway needs a named speaker and a real number. No vague generalities, and nothing
invented. If there is no recording or transcript for a session, it does not get a
breakdown.

## Adding a session

1. Copy an existing file in `articles/` as the template.
2. Set the series tag, headline, deck, four metrics, video embed, and speaker list.
3. Add a card to the grid in `index.html`, matching the surrounding markup. Set
   `data-series` so it colour codes, and point `vc__read` at the new article.
4. For the YouTube embed use `https://www.youtube.com/embed/VIDEO_ID`, and for the card
   thumbnail `https://img.youtube.com/vi/VIDEO_ID/maxresdefault.jpg`. `VIDEO_ID` is the
   part after `watch?v=`.

## Deploying by CLI instead

`./publish.sh` pushes the current directory straight to Netlify. It needs the Netlify CLI
authenticated on your machine, which is separate from GitHub access.
