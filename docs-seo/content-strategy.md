# Vidow Docs — Content Strategy & SEO Action Plan

> Based on DataForSEO keyword research (2026-04-08, US/English)

## Top 10 Easiest-to-Rank Opportunities

Sorted by best effort-to-impact ratio (low difficulty + meaningful volume):

| # | Keyword | Volume | Difficulty | Action |
|---|---|---|---|---|
| 1 | video downloader professional chrome extension | 2,400 | 4 | Optimize `billing/plans.mdx` title + description |
| 2 | how to download a video from any website | 2,900 | 7 | Rewrite `quickstart.mdx` around this exact phrase |
| 3 | m3u8 downloader online | 210 | 6 | Add to `guides/download-hls-streams.mdx` H2 |
| 4 | best video downloader extension for chrome | 480 | 8 | Create NEW comparison/landing page |
| 5 | hls downloader chrome | 480 | 11 | Optimize `features/stream-detection.mdx` |
| 6 | video downloader pro chrome extension | 2,400 | 11 | Secondary keyword for `billing/plans.mdx` |
| 7 | pinterest video downloader | 60,500 | 11 | Create NEW platform guide (if supported) |
| 8 | download hls stream | 1,300 | 12 | Already have page — optimize title/desc |
| 9 | how to download video from website | 2,900 | 15 | Optimize `quickstart.mdx` |
| 10 | m3u8 downloader | 2,400 | 18 | Optimize `guides/download-hls-streams.mdx` title |

## New Pages to Create

### 1. Video Tools Page (`features/video-tools.mdx`)
**Target keywords:**
- video compressor (90,500 vol, diff 65)
- video to gif (90,500 vol, diff 33)
- video format converter

**Why:** The backend has VideoTool enum with: Convert, Compress, AudioExtractor, Trim, VideoToGif, MergeVideos, AddAudio. These are fully built web app features with zero documentation. "video to gif" at 90.5K volume and difficulty 33 is a huge opportunity.

### 2. Platform Download Guides (if extension supports these sites)
**Potential pages:**
- `guides/download-from-facebook.mdx` — "download facebook video" (90.5K, diff 18)
- `guides/download-from-instagram.mdx` — "instagram video downloader" (368K, diff 36)
- `guides/download-from-tiktok.mdx` — "tiktok video downloader" (246K, diff 27)
- `guides/download-from-pinterest.mdx` — "pinterest video downloader" (60.5K, diff 11)
- `guides/download-from-reddit.mdx` — "reddit video downloader" (33.1K, diff 26)

**Why:** These platform-specific terms have massive volume with low-to-moderate difficulty. Even if Vidow doesn't have platform-specific detectors (like the Vimeo one), it still detects HLS/MP4 streams from these sites. Each page should explain how Vidow's universal detection works on that platform.

### 3. "Best Video Downloader Extension" Comparison Page
**Target:** "best video downloader chrome extension" (480, diff 8)
**Format:** Feature comparison table, Vidow vs generic alternatives (without naming competitors directly). Focus on what makes Vidow different: HLS/DASH support, format conversion, cloud sync, Chromecast.

## Global Rebranding Checklist

Every page needs:
- [ ] Replace "SaveMate" → "Vidow" (200+ occurrences across 31 files)
- [ ] Replace `savemate.io` → `vidow.io` / `app.vidow.io` (30+ occurrences)
- [ ] Replace Chrome Web Store extension ID `lejgkageoahacjmljeogapbkhbfldigd` → Vidow's actual CWS ID
- [ ] Replace `x.com/savemate_io` → Vidow's X handle
- [ ] Update `docs.json`: name, anchors, navbar, footer
- [ ] Update logo paths if different

## Factual Corrections Required

These must be fixed regardless of SEO:

### privacy.mdx (9 issues)
1. "No browsing history or visited URLs" — FALSE (extension stores tab URLs, sends to server)
2. "No analytics or tracking data" — MISLEADING (UTM params on all outbound links)
3. "Session token for logged-in users" — WRONG (stores boolean flag + device_key, not token)
4. "Login credentials (email and password)" — WRONG (extension never handles credentials)
5. Missing: device_key and anonymous device tracking
6. Missing: tabs and webRequest permissions from table
7. "Accessing your browsing history" listed as not requested — MISLEADING
8. "Cloud upload metadata" — not handled by extension
9. Domain references need updating

### installation.mdx
- "No browsing data is collected or transmitted" — FALSE
- "No analytics or tracking scripts" — MISLEADING

### supported-browsers.mdx
- "All processing is local — no browsing data is sent anywhere" — FALSE
- Language list needs verification against actual _locales/

### stream-detection.mdx
- "No data is sent to external servers" — FALSE (lastResortFetch)

### faq.mdx
- "no data is collected, transmitted, or tracked" — FALSE (×2 occurrences)

### chromecast.mdx
- "No account required — casting works for anonymous users too" — verify against cast limit gating

## SEO Writing Guidelines

When rewriting pages for Vidow:

1. **Don't just find-replace SaveMate→Vidow.** Google will flag near-duplicate content. Each page needs genuinely rewritten intros, descriptions, and key paragraphs.

2. **Primary keyword in:** title tag, H1, meta description, first paragraph, at least one H2.

3. **Secondary keywords in:** H2 headings, body paragraphs naturally. Don't stuff.

4. **Meta descriptions:** 150-160 characters, include primary keyword, end with value prop or CTA.

5. **Internal linking:** Each page should link to 2-3 related pages. Use keyword-rich anchor text (e.g., "learn how to download HLS streams" not "click here").

6. **Schema markup:** Mintlify handles basic SEO. For FAQ pages, use Accordion components (Mintlify renders them as FAQ schema).

7. **URL structure:** Keep current paths — they're clean and descriptive. Don't change slugs.

## Priority Order for Implementation

1. **Phase 1: Rebrand + Fix Errors** — Global find-replace + fix all factual inaccuracies
2. **Phase 2: SEO Optimization** — Rewrite titles/descriptions/intros per keyword mapping
3. **Phase 3: New Content** — Create video tools page, platform guides
4. **Phase 4: Link Building** — Internal linking structure, external outreach
