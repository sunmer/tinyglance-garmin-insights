# Tinyglance: Garmin Connect IQ market insights pack

Collected October 22-24, 2026 for Tinyglance (Garmin watch apps and faces).
Purpose: input for a product analytics agent. Read this file first.

## Questions this pack answers

1. Where is demand on the Connect IQ store, and where is supply weak?
2. What do users complain about and ask for (store reviews, Reddit)?
3. How large is search demand outside the store (Google Ads, Trends)?
4. Who already competes (store apps, ChatGPT/Claude data connectors)?
5. What should Pip (a step-powered pet watch face) fix before launch?

## Folders

| Folder | Contents |
| --- | --- |
| `01-connect-iq-store` | `catalog_all_40723` (every face, app, data field and widget the newest-first list returned; JSON and CSV, gzip). `ranked_lists_2038_apps.json` (most popular, trending, highest rated, hot fresh, top paid, per-type and curated shelf ranks, with SEK prices). Store keyword search results. Niche supply table. Category id map. |
| `02-reviews` | Reviews for 393 popular/low-rated apps (43,977) and 42 Pip peers (2,546), with rating distributions. `pip_peers_tagged_1200.json`: theme tags plus English translation (Azure OpenAI gpt-5.5). Negative-theme counts per app. Quote extracts. |
| `03-reddit` | Bright Data Reddit Posts dataset: 404 keyword-matched posts (2,879 comments), 587 top posts this year from 8 subreddits (8,322 comments), 12 key threads. Google `site:reddit.com` results. Theme summary. |
| `04-search-demand` | Google Ads Keyword Planner: historical metrics for 64 keywords (World, US, UK, DE, SE; 12 monthly values, competition, CPC) and keyword ideas. Google Trends 5-year groups and 12-month related queries. Google autocomplete. |
| `05-serp-youtube` | Google SERPs for niche queries (organic, People also ask, AI Overview flag). YouTube top videos per query. |
| `06-competitors` | Store flood statistics (approvals per quarter, bulk developers). Pip peer listings. Competitor profiles (Fitness AI Connector, freddy, open-source Garmin MCP servers, ROXZONE, Rack). |
| `07-reports` | Human-written findings: store analysis, top-3 opportunities, deep dive, AI connector triage, Pip peer reviews, Pip listing rules. |
| `08-scripts` | Collection scripts (Python). Keys come from environment variables; none are included. |

## Field notes

- `downloads_floor` is Garmin's rounded bucket (0, 1, 10, 100, 1,000, 10,000, 50,000, 100,000, 500,000, 1,000,000, ...), not an exact count.
- Catalog `type`: `watchface`, `watch-app`, `datafield`, `widget`. In `ranked_lists`, `type` ids are 1 face, 2 app, 3 widget, 4 data field, 5 music.
- Dates ending in `_ms` are Unix milliseconds. `first_approval_ms` is the best release date.
- Prices are SEK (store priced for a Swedish session).
- Ranked lists stop at 120 items per list; the newest-first catalog is the full-coverage source.
- Keyword Planner `avgMonthlySearches` is a 12-month average (Oct 2025 - Sep 2026). "garmin connect+" reports the volume for "garmin connect"; use "garmin connect plus".
- Google Trends values are relative (0-100 within each comparison group). Do not compare across groups.
- Theme counts from keyword matching are English-biased; the tagged Pip-peer set is translated.

## Privacy

Reviewer and Reddit user identities are replaced by salted hashes (`u_xxxxxxxxxx`), so authors can be grouped but not identified. Avatars, user ids, karma and bios are removed. Email addresses in free text are replaced by `[email]`. Developer display names and listing data are public business information and kept.

## Headline findings

- Face approvals grew from 128 per quarter (2023 Q1) to 5,889 (2026 Q3). In 2026, 28 bulk developers made 51% of new faces; 81% of 2026 faces have fewer than 100 downloads.
- Watch-app approvals grew from about 20-50 per quarter to 1,229 (2026 Q3), mostly first-time developers.
- Biggest functional gap on Reddit: strength training (show last weight and reps, progression). Also AI on your own data, HRV/recovery, women's health.
- Search: "garmin mcp" grew from 320 to 6,600-8,100 searches per month in 12 months. "strength training app" 12,100/month worldwide (US CPC USD 44). Garmin-specific niche terms are small (tens to hundreds).
- Chat-with-Garmin-data connectors already exist with official API access (Fitness AI Connector, USD 3/month, 60,000+ users claimed; freddy, USD 49/year).
- Pip peers: readability on MIP screens, more data fields, choosing the character and more content drive ratings. No step-powered pet has more than about 10,000 downloads.
