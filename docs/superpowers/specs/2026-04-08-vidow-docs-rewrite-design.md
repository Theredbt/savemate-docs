# Vidow Documentation Site — Full Rewrite Design

> Date: 2026-04-08
> Branch: Vidow (savemate-docs repo)
> Status: Design approved

## 1. Goal

Rewrite the entire Vidow documentation site (currently branded "SaveMate") from scratch. Every page gets completely original copy — zero sentences carried over from savemate.io — to avoid duplicate content penalties. The rewrite also fixes factual inaccuracies, adds missing feature documentation, creates new SEO-optimized pages, and targets high-value keywords identified through DataForSEO research.

## 2. Scope

### 2.1 Existing Pages (31 — rewrite from scratch)

| Group | Pages |
|---|---|
| Core | `index.mdx`, `quickstart.mdx`, `glossary.mdx`, `privacy.mdx` |
| Extension (4) | `extension/installation.mdx`, `extension/pinning.mdx`, `extension/supported-browsers.mdx`, `extension/settings.mdx` |
| Features (6) | `features/stream-detection.mdx`, `features/video-downloads.mdx`, `features/format-conversion.mdx`, `features/chromecast.mdx`, `features/cloud-storage.mdx`, `features/video-library.mdx` |
| Guides (9) | `guides/download-hls-streams.mdx`, `guides/download-from-vimeo.mdx`, `guides/youtube-and-chrome-extensions.mdx`, `guides/tips-and-tricks.mdx`, `guides/setup-google-drive.mdx`, `guides/setup-dropbox.mdx`, `guides/setup-aws-s3.mdx`, `guides/setup-cloudflare-r2.mdx`, `guides/copyright-and-fair-use.mdx` |
| Account (3) | `account/registration.mdx`, `account/settings.mdx`, `account/security.mdx` |
| Billing (3) | `billing/plans.mdx`, `billing/lifetime.mdx`, `billing/manage.mdx` |
| Support (2) | `support/faq.mdx`, `support/troubleshooting.mdx` |

### 2.2 New Pages (12)

| Group | Pages |
|---|---|
| Video Tools (7) | `tools/video-compressor.mdx`, `tools/video-trimmer.mdx`, `tools/video-to-gif.mdx`, `tools/merge-videos.mdx`, `tools/add-audio.mdx`, `tools/hls-player.mdx`, `tools/cast-player.mdx` |
| Platform Guides (5) | `guides/download-from-facebook.mdx`, `guides/download-from-instagram.mdx`, `guides/download-from-tiktok.mdx`, `guides/download-from-pinterest.mdx`, `guides/download-from-reddit.mdx` |

### 2.3 Config File

`docs.json` — full rewrite of brand, navigation, anchors, footer, navbar.

**Total: 43 content pages + 1 config file.**

## 3. Brand Constants

All pages use these values consistently:

| Key | Value |
|---|---|
| Brand name | Vidow |
| Domain | vidow.io |
| Chrome Web Store ID | hkdmdpdhfaamhgaojpelccmeehpfljgf |
| CWS URL | `https://chromewebstore.google.com/detail/hkdmdpdhfaamhgaojpelccmeehpfljgf` |
| X/Twitter | `x.com/vidow_io` |
| Contact | `vidow.io/contact` |
| Blog | `vidow.io/blog` |
| Downloads page | `vidow.io/downloads` |
| Pricing | `vidow.io/pricing` |
| Languages | 59 |
| Extension version | 2.0 |
| Brand colors | Keep existing blue (#2563EB primary, #3B82F6 light, #1D4ED8 dark) unless user provides Vidow-specific colors |

## 4. Navigation Structure

### docs.json navigation update

```
Tabs > Guides:
  Getting Started:
    - index
    - quickstart

  Browser Extension:
    - extension/installation
    - extension/pinning
    - extension/supported-browsers
    - extension/settings

  Features:
    - features/stream-detection
    - features/video-downloads
    - features/format-conversion
    - features/chromecast
    - features/cloud-storage
    - features/video-library

  Video Tools:                          # NEW GROUP
    - tools/video-compressor
    - tools/video-trimmer
    - tools/video-to-gif
    - tools/merge-videos
    - tools/add-audio
    - tools/hls-player
    - tools/cast-player

  Download Guides:
    - guides/download-hls-streams
    - guides/download-from-vimeo
    - guides/download-from-facebook     # NEW
    - guides/download-from-instagram    # NEW
    - guides/download-from-tiktok       # NEW
    - guides/download-from-pinterest    # NEW
    - guides/download-from-reddit       # NEW
    - guides/youtube-and-chrome-extensions
    - guides/tips-and-tricks

  Cloud Storage Setup:
    - guides/setup-google-drive
    - guides/setup-dropbox
    - guides/setup-aws-s3
    - guides/setup-cloudflare-r2

  Account:
    - account/registration
    - account/settings
    - account/security

  Billing:
    - billing/plans
    - billing/lifetime
    - billing/manage

  Support:
    - support/faq
    - support/troubleshooting
    - glossary

  Legal:
    - privacy
    - guides/copyright-and-fair-use

Global anchors:
  - Website → https://vidow.io
  - Blog → https://vidow.io/blog
  - Downloads → https://vidow.io/downloads

Navbar:
  - Contact → https://vidow.io/contact
  - CTA: "Get Vidow" → https://vidow.io/downloads

Footer socials:
  - x: https://x.com/vidow_io
```

## 5. SEO Strategy

### 5.1 Keyword Targeting

Full keyword research is in `docs-seo/keyword-research.md`. Page-to-keyword mapping is in `docs-seo/page-keyword-mapping.md`.

Top opportunities by effort-to-impact ratio:

| Keyword | Volume | Difficulty | Target Page |
|---|---|---|---|
| video downloader professional chrome extension | 2,400 | 4 | billing/plans |
| how to download a video from any website | 2,900 | 7 | quickstart |
| m3u8 downloader online | 210 | 6 | guides/download-hls-streams |
| best video downloader extension for chrome | 480 | 8 | extension/installation |
| hls downloader chrome | 480 | 11 | features/stream-detection |
| pinterest video downloader | 60,500 | 11 | guides/download-from-pinterest |
| download hls stream | 1,300 | 12 | guides/download-hls-streams |
| download facebook video | 90,500 | 18 | guides/download-from-facebook |
| m3u8 downloader | 2,400 | 18 | guides/download-hls-streams |
| video downloader extension for chrome | 5,400 | 19 | extension/installation |
| instagram video downloader | 368,000 | 36 | guides/download-from-instagram |
| tiktok video downloader | 246,000 | 27 | guides/download-from-tiktok |
| video to gif | 90,500 | 33 | tools/video-to-gif |
| video compressor | 90,500 | 65 | tools/video-compressor |

### 5.2 On-Page SEO Rules

Every page follows:
- **Title:** `[Primary Keyword] — [Value Prop with Vidow]`
- **Meta description:** 150-160 chars, primary keyword in first half, CTA in second half
- **H1** = page title (contains primary keyword)
- **First paragraph** includes primary keyword naturally within first 2 sentences
- **H2s** include secondary keywords where natural
- **Internal links** use keyword-rich anchor text
- **Each page** links to 2-3 related pages
- **FAQ sections** use Accordion components (Mintlify renders as FAQ schema)

### 5.3 Content Differentiation

To avoid duplicate content with savemate.io:
- Every page is written from scratch — no sentences, paragraphs, or structures copied
- Different heading hierarchy and information ordering
- Different examples and explanations
- Fresh analogies and descriptions
- Vidow-specific voice: direct, technical-but-accessible, no corporate filler

## 6. Factual Accuracy — Privacy & Data Collection

The privacy page and all pages that reference data collection must reflect the verified truth from the codebase audit.

### 6.1 What Vidow Stores Locally

- Extension preferences: theme, badge mode, blocked sites, format filters, download path, minimum file size
- Detected video metadata per tab: page URL, video URLs, titles, thumbnails, quality info, stream type (cleared on tab close or navigation, auto-cleaned after 24h)
- Authentication state: `logged_in` boolean, `upgraded` flag, `device_key` identifier, `device_claimed` flag, auth failure count + timestamps
- HD download limit cache
- Saved video hashes (for library sync indicator)

### 6.2 What Vidow Sends to vidow.io

- **Last-resort video detection:** Page URL sent to `api/video/fetch-video-info` when network interception doesn't find videos
- **Save to library:** Video title, page link, thumbnail URL sent to `api/videos`
- **Bug reports:** Page URL, browser name, error details sent to `api/reports` (user-initiated only)
- **Device claim:** Device key sent to `api/device/claim` on first login (merges anonymous activity)
- **Limit checks:** Device key sent to `api/streaming/check-limit` and `api/streaming/check-cast-limit`
- **Auth status:** Session cookies sent with `GET /api/user` to check login state
- **Outbound links:** UTM parameters (utm_source=extension, utm_medium, utm_campaign, utm_content) + browser name + extension version appended to all URLs that open vidow.io

### 6.3 What Vidow Does NOT Collect

- Passwords or login credentials (authentication via session cookies set on vidow.io web app)
- General browsing history (only pages where videos are detected or user takes explicit action)
- Keystrokes, form data, clicks, mouse position, scroll activity
- Payment information (Stripe handles all billing server-side)
- Video content or downloaded files
- Location data
- Personal communications

### 6.4 Extension Permissions — Complete Table

| Permission | Purpose |
|---|---|
| `tabs` | Associate detected video streams with their originating tab, update badge icon per tab, detect tab navigation/close to clear data, open install/uninstall/download pages |
| `webRequest` | Intercept HTTP response headers to detect video media streams (HLS, DASH, MP4) and capture request headers for authenticated stream replay |
| `declarativeNetRequest` | Fallback download via Content-Disposition header injection; streaming bridge header forwarding for cast/stream player pages |
| `storage` | Persist extension state: preferences (sync), detected videos + auth state + limit cache (local) |
| `downloads` (optional) | Requested at runtime when user downloads. Triggers chrome.downloads.download() with save-as dialog |
| `<all_urls>` (host) | Network monitoring for video detection across all domains; content script for DOM scanning and thumbnail extraction; manifest fetching from arbitrary CDNs |

### 6.5 Pages That Must Reflect This

These pages previously contained inaccurate claims. The rewrite must use the corrected data above:
- `privacy.mdx` — full rewrite with accurate data collection disclosure
- `extension/installation.mdx` — remove "no data collected" claim
- `extension/supported-browsers.mdx` — remove "no browsing data sent" claim
- `features/stream-detection.mdx` — remove "no data sent to external servers" claim
- `support/faq.mdx` — remove "no data collected or tracked" claims (2 occurrences)

## 7. Page Templates

### 7.1 Video Tool Page Template

```
---
title: "[Tool Name] — [Action] with Vidow"
description: "[150-160 char description with primary keyword]"
---

[1-2 sentence intro with primary keyword]

## How to [action]

<Steps> ... </Steps>

## Supported formats

| Format | ... |

## Options and settings

[Tool-specific controls]

## Free vs Professional

| Feature | Free | Professional |
| ... |

## How it works

[Brief technical explanation — all processing in browser, WebAssembly]

## Related tools

<CardGroup> links to related tool pages </CardGroup>
```

### 7.2 Platform Download Guide Template

```
---
title: "[Platform] Video Downloader — Download [Platform] Videos with Vidow"
description: "[150-160 char description targeting '[platform] video downloader']"
---

[Intro targeting primary keyword — explain Vidow works on [Platform] via universal detection]

## How Vidow detects [Platform] videos

[Explain that [Platform] uses HLS/MP4/etc, and Vidow's network monitoring picks it up]

## Step-by-step: Download a [Platform] video

<Steps> platform-specific tips (e.g., "play the video first") </Steps>

## Available quality options

| Quality | ... |

## [Platform]-specific tips

[Embedded players, mobile links opened on desktop, etc.]

## Frequently asked questions

<AccordionGroup>
  3-4 platform-specific FAQs
</AccordionGroup>

## Get started

<Card> Install Vidow CTA </Card>
```

## 8. Execution Approach

All 43 pages rewritten from scratch in a single pass. No content from savemate.io carried over. Order of execution:

1. **docs.json** — brand config, navigation with new groups
2. **Core pages** — index, quickstart, glossary, privacy (highest SEO value)
3. **Extension pages** (4) — installation, pinning, browsers, settings
4. **Feature pages** (6) — stream-detection, downloads, conversion, chromecast, cloud, library
5. **Video tool pages** (7) — NEW: compressor, trimmer, gif, merge, add-audio, hls-player, cast-player
6. **Download guides** (9 existing + 5 new = 14) — HLS, Vimeo, Facebook, Instagram, TikTok, Pinterest, Reddit, YouTube explanation, tips
7. **Cloud storage setup** (4) — Google Drive, Dropbox, AWS S3, Cloudflare R2
8. **Account pages** (3) — registration, settings, security
9. **Billing pages** (3) — plans, lifetime, manage
10. **Support pages** (2) — FAQ, troubleshooting

## 9. Quality Criteria

- Zero sentences duplicated from savemate.io docs
- Every page has unique title + meta description targeting researched keywords
- All factual claims about data collection match codebase reality (Section 6)
- All URLs point to vidow.io (no savemate.io references)
- Extension ID is hkdmdpdhfaamhgaojpelccmeehpfljgf everywhere
- Internal links use keyword-rich anchor text
- 59 languages mentioned (not 3)
- All 7 video tools documented
- All 5 extension permissions accurately described
- Mintlify components used consistently (Steps, Cards, Accordions, Tips, Warnings, Notes, Info)

## 10. Out of Scope

- Logo/favicon file changes (user swaps these manually)
- Custom CSS or Mintlify theme modifications
- Deployment/hosting setup (Mintlify handles this)
- Blog content creation
- Landing page copy (separate from docs)
- Analytics/tracking integration on docs site
