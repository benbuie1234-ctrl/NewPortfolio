# Ben Buie — Portfolio

Freelance video editor portfolio. Single static page, no build step.

`index.html` is self-contained: all CSS and JS are inline. The only external
dependencies are Google Fonts (Hanken Grotesk), YouTube thumbnails/embeds,
and Instagram reel embeds.

## Local preview

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## Before going live

Search `index.html` for these markers — each one is a claim that still needs
real numbers:

| Marker | What to change |
| --- | --- |
| `[BOOKING_URL]` | Set `var BOOKING_URL` near the bottom of the file to your Cal.com / Calendly link. Left empty, every "Book a call" button falls back to the Instagram DM popup. |
| `[METRIC]` | The `000M` views, `000+` videos, and the three `000k` view counts on the result cards. |
| `[RATING]` | The "4.9 · 17+ creators" hero badge. 17 is real; the rating is a placeholder. |
| `[REASSURE]` | "48-hour turnaround", "Revisions included", "You keep the project files". Appears three times — set to what you actually promise, or delete. |

## Deploy

Configured for Cloudflare Workers static assets via `wrangler.jsonc`:

```bash
npx wrangler deploy
```

`.assetsignore` keeps config and repo files out of the deployed bundle.
