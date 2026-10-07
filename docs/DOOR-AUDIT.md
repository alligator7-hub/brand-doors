# Door audit — 2026-10-07

Read-only against live Pages, plus the fixes in this branch. No DNS change. No workflow run. No paid deploy.

Scope: the four doors in this repo, the quiet index, `404.html`, and a read of the live Owl Offers door in `alligator7-hub/owl-offers-door`. Owl's repo was not edited.

## Prior audit (PR #2)

[PR #2](https://github.com/alligator7-hub/brand-doors/pull/2) audited `a3ff720`, before merge and before the Mindful Wealth name-safe replace (`9d98537`). Its `AUDIT.md` is stale. Do not merge that PR. This file continues the findings that are still true.

| Finding | Status |
| --- | --- |
| Lock pass on the four doors (no buy path, no Owl copy on those pages, no advice pitch, no invented Mindful Wealth inbox) | Still true after the name-safe replace. Re-checked in this branch. |
| GitHub Pages not enabled | Closed. `https://alligator7-hub.github.io/brand-doors/` returned HTTP 200 on 2026-10-07. Pages source is the Actions workflow. |
| `404.html` used `href="./"`, which misses the site root on a nested 404 | Closed in this branch. The home link is `/brand-doors/`. |
| Instagram, TikTok, and Threads could not be verified from a server | Still open. Instagram returned a login wall, then HTTP 429. TikTok and Threads returned HTTP 200 shells. That does not prove the handle exists. |
| Mindful Wealth TikTok double-L needed a browser look | Still open as a browser confirm. The door no longer links TikTok (`9d98537`). The README now matches that. The recorded spelling stays `@mindfullwealthgroup`. Do not "correct" it. |
| Creative Faith has no TikTok or email, and Mindful Wealth has no email | Closed as intentional. Still true. |
| YouTube channel titles matched the brands on 2026-09-02 | Not re-proven from this server. Channel oEmbed returns HTTP 404 here for these IDs and for known-good channels. The channel URLs themselves return HTTP 200. Not marked broken. |

## This pass

| Check | Result |
| --- | --- |
| Broken links on the four doors | None confirmed. YouTube, Instagram, TikTok, and Threads did not return a clean 404 for a real profile. Mailto links were not sent. Threads was updated from `threads.net` to `threads.com` because the old host already forwards there. |
| Placeholder copy | None. No lorem, TODO, or TBD. The Creative Faith frame says the work is not reproduced here. That line is the lock, not filler. "Calm money" is the name-safe door, not an unfinished title. |
| Open Graph | Missing on all four doors. Added in this branch: canonical, `og:*`, `twitter:*`, and a 1200×630 `og.png` per door. The quiet index stays `noindex` and has no share card. Owl already has Open Graph on its own door, including `og.png`. |
| Unlock-phrase docs | There was no bio sheet in this repo. `docs/BIO-UNLOCK-SHEETS.md` is the draft. Owl's Instagram and TikTok lines match the 2026-09-14 bio SET (104 and 56 characters). The other four are drafted from the live door sentences. No comment-to-unlock keyword is defined. |
| Secrets | None added. No tokens, no Metricool ids, no mailbox passwords. |

## Owl Offers (other repo, not changed)

Live home `https://alligator7-hub.github.io/owl-offers-door/` returned HTTP 200 and already has Open Graph.

| Item | Status |
| --- | --- |
| Open PR to put `owloffers.com` on Pages (`CNAME`, serve from `/`) | Still open. Do not merge from this wave. Merging before DNS answers would redirect the github.io door onto a host that does not answer. |
| `/sample` and `/start` HTTP status | Still HTTP 404 to a plain client. Humans get the page through the `404.html` SPA fallback. Left as a non-lock note in the Owl repo. |
| Kit, Stripe, Linktree on the door | Still absent. Intentional. |

## Locks re-checked on this branch

Visitor HTML still has no buy link, no first-step price, no merch-store hostname, and no city names. Owl is named only in `README.md` and `docs/`, not on the four door pages. Mindful Wealth's public title and share card say "Calm money", not the firm name. The quiet index still lists "Mindful Wealth Group" as the noindex map label. That split is unchanged.

## Deepen — 2026-10-07

`docs/BIO-UNLOCK-SHEETS.md` already had a first-pass card for Owl Offers, Creative Faith, and Alligator7. This pass adds the per-network card that was missing: YouTube description where a channel is on record, TikTok bio where a handle is on record, and an explicit empty row where no handle is on record.

- Owl's 104-character and 56-character lines are unchanged. TikTok still says to set the website only if that field exists, and to replace the faith-lane bio. YouTube still uses the 104-character line and names the public channel `UCcRA06_69nWowmwo1DmNtfg`. Thread posts are not in the sheet.
- Creative Faith gained a YouTube description taken from the door sentence. TikTok, Threads, and Facebook have no handle on record, so those rows paste nothing.
- Alligator7 gained a TikTok line (the 79-character Instagram draft fits the 80-character cap) and a YouTube description taken from the door sentence. The live Linktree website and the live merch-store website stay until a named k. Threads and Facebook have no handle on record.

No profile was edited. No post was scheduled. No Metricool id, page id, mailbox password, or token was added.
