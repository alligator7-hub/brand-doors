# Audit — brand doors

Audited: every visitor-facing page on PR #1 (`cursor/four-brand-doors-d53b` @ `a3ff720`).
`main` at audit time contained only `README.md`; all pages live on the PR branch.

Locks checked on every HTML, CSS, SVG, and workflow file (case-insensitive grep plus manual read):
no buy links · no Owl Offers copy · no `$497` · no `shopowloffers` · no Olympia/Tumwater/Lacey ·
Creative Faith has no store · Alligator7 is education not advice · Mindful Wealth Group has no invented inbox or product ·
no fifth brand.

## Per page

| Page | Result | Notes |
| --- | --- | --- |
| `/` (`index.html`) | PASS | Four brand names as links only. `noindex`. No copy, no CTA, no fifth brand. |
| `/alligator7/` | PASS | "Education, not advice. No trade calls. No income stories." Footer: "Education only. Not financial advice." Keyword tape includes `NO SIGNALS`. CTA is the YouTube channel; no purchase path. |
| `/tryharderthanks/` | PASS | CTA is `mailto:tryharderthanks@gmail.com`. Supporting links Instagram/TikTok/Threads/YouTube only. No X/Twitter, no LinkedIn, no income story, no product. |
| `/mindfulwealthgroup/` | PASS | "No products. No accounts managed here. No advice." Note line "Not financial advice. Not an advisory." No email/inbox anywhere on the page. CTA is Instagram. |
| `/creativefaith/` | PASS | "This door does not sell it." No store, cart, price, or buy link. Art is not reproduced (placeholder frame states so). CTA is Instagram follow; YouTube only as supporting link. |
| `/404.html` | PASS | Single "home" link, no brand copy. |

Locked-term grep across the whole branch returned zero hits for: `owl` (outside README's own "Not Owl Offers" guardrail line), `497`, `shopowl`, `olympia`, `tumwater`, `lacey`, `buy`, `shop`, `store`, `cart`, `price`, `linktree`, `twitter`, `linkedin`, `inbox`, `aum`.
CSS `content:` strings and SVG `<text>` nodes were inspected; nothing hidden there (only a `·` separator and a `TH` favicon glyph).

## Facts checked

| Fact | Status |
| --- | --- |
| YouTube `UCKOJdD9WkZSSrFBQMr-6TzQ` | Resolves; channel title "Alligator7" |
| YouTube `UCFIVGeKCd2I7eOsSukz2KWw` | Resolves; channel title "Tryharderthanks" |
| YouTube `UCgpTk58s8POkRvd8Z_JnYBQ` | Resolves; channel title "Mindfulwealthgroup" |
| YouTube `UCvzN-wSuF-MYHrF6g1cDWpA` | Resolves; channel title "Creative Faith Innovations" |
| Instagram `@alligator712`, `@tryharderthanks`, `@mindfulwealthgroup`, `@creativefaithinnovations` | Unverified from server — Instagram returns an identical login wall for real and fabricated handles |
| TikTok `@alligator777777777`, `@tryharderthanks`, `@mindfullwealthgroup` (double L) | Unverified from server — TikTok returns an identical bot wall for real and fabricated handles. Owner should confirm the double-L spelling in a browser. |
| Threads `@tryharderthanks` | Unverified from server (same wall) |
| Emails `alligator7official@gmail.com`, `tryharderthanks@gmail.com` | Present in source as supplied; not testable without sending mail |

## Missing / worth knowing (not lock violations)

- **GitHub Pages is not enabled.** `has_pages: false`; `GET /repos/alligator7-hub/brand-doors/pages` returns 404. Nothing is live yet. After PR #1 merges, set Settings → Pages → Source: **GitHub Actions**. The workflow does not pass `enablement: true` to `configure-pages`, so the first `main` push will fail the deploy job until that setting is flipped by hand.
- `404.html` links home with `href="./"`. On a project site served at `/brand-doors/`, a miss at `/brand-doors/x/y` resolves that link to `/brand-doors/x/`, which is also a miss. `href="/brand-doors/"` would always land. Cosmetic; not a lock.
- Creative Faith has no TikTok link and no email. Mindful Wealth Group has no email. Both are deliberate per the PR guardrails (no guessed handle, no invented inbox).
- Root `index.html` has no `<h1>`; fine for a deliberately quiet index.

## Verdict

Clean. No lock violations on any page. No fix PR required. PR #1 was not merged as part of this audit.
