# Vidow Documentation Site — Full Rewrite Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Rewrite all 43 documentation pages from scratch for the Vidow brand with SEO optimization, fix factual errors, and add 12 new pages (7 video tools + 5 platform guides).

**Architecture:** Mintlify-powered docs site. Each `.mdx` page is independent — no shared components or build dependencies. `docs.json` controls navigation and branding. All pages use Mintlify components (Steps, Cards, Accordions, Tips, Warnings, Notes, Info, CardGroup).

**Tech Stack:** Mintlify docs framework, MDX, JSON config

**Reference files (read before writing any page):**
- Spec: `docs/superpowers/specs/2026-04-08-vidow-docs-rewrite-design.md`
- Keywords: `docs-seo/keyword-research.md`
- Keyword mapping: `docs-seo/page-keyword-mapping.md`
- Content strategy: `docs-seo/content-strategy.md`

**Brand constants (use in every page):**
- Brand: **Vidow**
- Domain: **vidow.io**
- CWS ID: **hkdmdpdhfaamhgaojpelccmeehpfljgf**
- CWS URL: `https://chromewebstore.google.com/detail/hkdmdpdhfaamhgaojpelccmeehpfljgf`
- X: `x.com/vidow_io`
- Languages: **59**
- Extension version: **2.0**

**Writing rules (apply to ALL pages):**
- Zero sentences copied from the savemate.io docs (the existing files). Write everything fresh.
- Primary keyword appears in: title, description, H1, first paragraph, at least one H2
- Meta descriptions: 150-160 characters
- Each page links to 2-3 related pages with keyword-rich anchor text
- Use Mintlify components consistently
- Voice: direct, technical-but-accessible, no corporate filler

---

## Task 1: Update docs.json config

**Files:**
- Modify: `docs.json`

- [ ] **Step 1: Rewrite docs.json**

Replace the entire file with:

```json
{
  "$schema": "https://mintlify.com/docs.json",
  "theme": "mint",
  "name": "Vidow",
  "colors": {
    "primary": "#2563EB",
    "light": "#3B82F6",
    "dark": "#1D4ED8"
  },
  "favicon": "/favicon.svg",
  "navigation": {
    "tabs": [
      {
        "tab": "Guides",
        "groups": [
          {
            "group": "Getting Started",
            "pages": ["index", "quickstart"]
          },
          {
            "group": "Browser Extension",
            "pages": [
              "extension/installation",
              "extension/pinning",
              "extension/supported-browsers",
              "extension/settings"
            ]
          },
          {
            "group": "Features",
            "pages": [
              "features/stream-detection",
              "features/video-downloads",
              "features/format-conversion",
              "features/chromecast",
              "features/cloud-storage",
              "features/video-library"
            ]
          },
          {
            "group": "Video Tools",
            "pages": [
              "tools/video-compressor",
              "tools/video-trimmer",
              "tools/video-to-gif",
              "tools/merge-videos",
              "tools/add-audio",
              "tools/hls-player",
              "tools/cast-player"
            ]
          },
          {
            "group": "Download Guides",
            "pages": [
              "guides/download-hls-streams",
              "guides/download-from-vimeo",
              "guides/download-from-facebook",
              "guides/download-from-instagram",
              "guides/download-from-tiktok",
              "guides/download-from-pinterest",
              "guides/download-from-reddit",
              "guides/youtube-and-chrome-extensions",
              "guides/tips-and-tricks"
            ]
          },
          {
            "group": "Cloud Storage Setup",
            "pages": [
              "guides/setup-google-drive",
              "guides/setup-dropbox",
              "guides/setup-aws-s3",
              "guides/setup-cloudflare-r2"
            ]
          },
          {
            "group": "Account",
            "pages": [
              "account/registration",
              "account/settings",
              "account/security"
            ]
          },
          {
            "group": "Billing",
            "pages": [
              "billing/plans",
              "billing/lifetime",
              "billing/manage"
            ]
          },
          {
            "group": "Support",
            "pages": [
              "support/faq",
              "support/troubleshooting",
              "glossary"
            ]
          },
          {
            "group": "Legal",
            "pages": ["privacy", "guides/copyright-and-fair-use"]
          }
        ]
      }
    ],
    "global": {
      "anchors": [
        {
          "anchor": "Website",
          "href": "https://vidow.io",
          "icon": "globe"
        },
        {
          "anchor": "Blog",
          "href": "https://vidow.io/blog",
          "icon": "newspaper"
        },
        {
          "anchor": "Downloads",
          "href": "https://vidow.io/downloads",
          "icon": "download"
        }
      ]
    }
  },
  "logo": {
    "light": "/logo/light.svg",
    "dark": "/logo/dark.svg"
  },
  "navbar": {
    "links": [
      {
        "label": "Contact",
        "href": "https://vidow.io/contact"
      }
    ],
    "primary": {
      "type": "button",
      "label": "Get Vidow",
      "href": "https://vidow.io/downloads"
    }
  },
  "contextual": {
    "options": ["view"]
  },
  "footer": {
    "socials": {
      "x": "https://x.com/vidow_io",
      "github": "https://github.com"
    }
  },
  "seo": {
    "indexHiddenPages": false
  },
  "feedback": {
    "thumbsRating": true
  }
}
```

- [ ] **Step 2: Create tools/ directory**

```bash
mkdir -p tools
```

- [ ] **Step 3: Commit**

```bash
git add docs.json
git commit -m "chore: rebrand docs.json to Vidow with new nav structure"
```

---

## Task 2: Core Pages — index.mdx

**Files:**
- Modify: `index.mdx`

**SEO target:** "video downloader" (201K vol, diff 37)
**Secondary:** online video downloader, browser video downloader, stream video downloader

- [ ] **Step 1: Rewrite index.mdx**

Write a completely new homepage for Vidow. Requirements:
- Title: "Vidow — Video Downloader Extension for Chrome, Edge & Brave"
- Description (150-160 chars): Include "video downloader" in first half
- Open with what Vidow is and what it does (1-2 sentences, include "video downloader")
- CardGroup with 6 feature cards: Stream Detection, Video Downloads, Format Conversion, Chromecast, Cloud Storage, Video Library — each with fresh descriptions (not copied from savemate.io)
- Steps component: Install → Browse → Save/Cast (3 steps, fresh wording)
- Card linking to quickstart
- "Free vs Professional" section with fresh copy explaining the tiers
- Card linking to billing/plans
- Include "online video downloader" and "browser video downloader" naturally in body text
- Link to at least 2-3 other pages with keyword-rich anchors

- [ ] **Step 2: Commit**

```bash
git add index.mdx
git commit -m "docs: rewrite index.mdx for Vidow with SEO optimization"
```

---

## Task 3: Core Pages — quickstart.mdx

**Files:**
- Modify: `quickstart.mdx`

**SEO target:** "how to download video from website" (2.9K vol, diff 15)
**Secondary:** download video from website, how to download a video from any website

- [ ] **Step 1: Rewrite quickstart.mdx**

Requirements:
- Title: "How to Download Video from Any Website — Quick Start Guide"
- Description: Include "download video from website" in first half
- "Install the extension" section with Steps (CWS link uses Vidow ID `hkdmdpdhfaamhgaojpelccmeehpfljgf`)
- "Download your first video" section with Steps — include "download video from any website" naturally
- "Create an account" section — link to `vidow.io/register`, mention Google SSO, explain it's optional
- "Next steps" CardGroup linking to 4 related pages
- Fresh wording throughout — different structure and examples from savemate.io version

- [ ] **Step 2: Commit**

```bash
git add quickstart.mdx
git commit -m "docs: rewrite quickstart.mdx for Vidow with SEO optimization"
```

---

## Task 4: Core Pages — privacy.mdx

**Files:**
- Modify: `privacy.mdx`

**SEO target:** "video downloader privacy policy"

- [ ] **Step 1: Rewrite privacy.mdx with accurate data**

This is the most critical page for factual accuracy. Requirements:
- Title: "Privacy & Security — How Vidow Protects Your Data"
- Must accurately reflect codebase reality (see spec Section 6 for exact data)
- Sections:
  1. "Processing happens in your browser" — table of local operations (detection, downloading, conversion, cloud upload direct-to-provider)
  2. "What Vidow stores in your browser" — preferences, detected video metadata, auth state (boolean + device key), limit cache
  3. "What Vidow sends to our servers" — last-resort detection (page URL), save-to-library (title/link/thumb), bug reports (user-initiated), device claim, limit checks, auth status via cookies, UTM params on outbound links
  4. "What Vidow does not collect" — passwords, general browsing history, keystrokes, payment info, video files, location
  5. "Extension permissions" — complete table with all 5 permissions + host permission, accurate descriptions
  6. "Cloud storage security" — OAuth providers, API key providers
  7. "Payment security" — Stripe handles everything
  8. "Account deletion" — link to vidow.io/settings/security
  9. "Contact" — link to vidow.io/contact
- Do NOT claim "no data is sent" or "no tracking" — be honest and specific
- Do NOT mention "login credentials (email and password)" — extension never handles these

- [ ] **Step 2: Commit**

```bash
git add privacy.mdx
git commit -m "docs: rewrite privacy.mdx with accurate data collection disclosure"
```

---

## Task 5: Core Pages — glossary.mdx

**Files:**
- Modify: `glossary.mdx`

**SEO target:** "video streaming glossary"

- [ ] **Step 1: Rewrite glossary.mdx**

Requirements:
- Title: "Glossary — Video Streaming & Download Terms Explained"
- Same categories: Streaming & Video, File Formats, Cloud Storage, Browser & Web
- Every definition must be freshly written — same concepts, different wording
- Include all existing terms + add: "Transmuxing", "Service Worker", "Manifest V3"
- Use AccordionGroup components (renders as FAQ schema)
- Reference Vidow where appropriate (e.g., "When Vidow detects an m3u8 file...")

- [ ] **Step 2: Commit**

```bash
git add glossary.mdx
git commit -m "docs: rewrite glossary.mdx for Vidow"
```

---

## Task 6: Extension Pages (4 pages)

**Files:**
- Modify: `extension/installation.mdx`
- Modify: `extension/pinning.mdx`
- Modify: `extension/supported-browsers.mdx`
- Modify: `extension/settings.mdx`

### extension/installation.mdx
**SEO:** "video downloader extension for chrome" (5.4K vol, diff 19)

- Title: "Install Vidow — Video Downloader Extension for Chrome, Edge & Brave"
- CWS link: `https://chromewebstore.google.com/detail/hkdmdpdhfaamhgaojpelccmeehpfljgf`
- Steps for installation
- Browser compatibility table (Chrome, Edge, Brave — fully supported; Firefox — coming soon)
- System requirements
- Privacy note — ACCURATE: "Vidow monitors network traffic locally to detect video streams. Page URLs are sent to Vidow servers only for fallback video detection on sites where network interception alone isn't sufficient." Do NOT say "no data collected."
- Settings overview
- Update info
- Include "best video downloader extension for chrome" naturally in body

### extension/pinning.mdx
- Title: "Pin Vidow to Your Browser Toolbar"
- Fresh Steps for pinning
- Why pin — detection indicator explanation (fresh wording)
- Browser-specific notes accordion

### extension/supported-browsers.mdx
- Title: "Supported Browsers — Chrome, Edge, Brave & More"
- Browser table, OS support, mobile note, minimum versions
- **59 languages** — list top 10-15, state "59 languages total, automatically matches your browser setting"
- Permissions table — complete with all 5 permissions + host, accurate descriptions
- "Why Chromium only" section

### extension/settings.mdx
- Title: "Extension Settings — Customize Detection, Downloads & Casting"
- Format options (video + audio tables)
- Minimum file size presets
- Download settings (management toggle, path)
- Chromecast toggle
- **Badge mode** (count vs dot) — this was missing from old docs
- **Theme** (light/dark/system) — this was missing from old docs
- Website controls (blocked sites)
- Save behavior note

- [ ] **Step 1: Rewrite all 4 extension pages**

Write each page from scratch following the requirements above. Every sentence must be original.

- [ ] **Step 2: Commit**

```bash
git add extension/
git commit -m "docs: rewrite extension pages for Vidow with accurate permissions"
```

---

## Task 7: Feature Pages (6 pages)

**Files:**
- Modify: `features/stream-detection.mdx`
- Modify: `features/video-downloads.mdx`
- Modify: `features/format-conversion.mdx`
- Modify: `features/chromecast.mdx`
- Modify: `features/cloud-storage.mdx`
- Modify: `features/video-library.mdx`

### features/stream-detection.mdx
**SEO:** "stream video downloader" (8.1K vol, diff 28)
- Title: "Stream Detection — Automatically Find HLS, DASH & MP4 Videos"
- How detection works (passive monitoring, stream ID, notification, user action) — fresh wording
- Supported stream types tables (adaptive: HLS/DASH, progressive: 16 formats, audio: 5 formats)
- Platform-specific: Vimeo enhanced detection
- Detection indicator explanation
- Stream metadata extracted (title, thumbnail, quality, file size, duration, source)
- Quality tiers table (SD through 8K + 60fps, free vs pro)
- Detection settings overview
- "Works with any site" note
- Do NOT say "no data sent to servers" — omit or say "detection runs in your browser with server-assisted fallback for complex sites"

### features/video-downloads.mdx
**SEO:** "download streaming video" (6.6K vol, diff 26)
- Title: "Video Downloads — Save Streaming Video in Any Quality"
- How to download (Steps)
- Quality table (free vs pro)
- HLS/DASH download process explanation
- Progressive download explanation
- Download limits (free: unlimited 720p, 3 HD/day; pro: unlimited)
- Supported formats table
- Download settings

### features/format-conversion.mdx
**SEO:** "hls to mp4 converter" (10 vol but high intent, growing)
- Title: "Format Conversion — Convert HLS & DASH Streams to MP4, MKV, MOV"
- Pro feature badge
- Video conversion table (MP4, MKV, MOV, WebM)
- Audio extraction table (MP3, AAC)
- How it works (Steps)
- Format comparison table
- Key details (local processing, quality preservation, auto-muxing, DASH SegmentBase)

### features/chromecast.mdx
**SEO:** "cast video to chromecast"
- Title: "Chromecast & AirPlay — Cast Detected Videos to Your TV"
- How to cast (Steps)
- Cast player features
- Availability — verify: casting may have limits for free users (cast limit check exists in code)
- Technical details
- Requirements

### features/cloud-storage.mdx
**SEO:** "cloud storage video sync"
- Title: "Cloud Storage — Sync Downloads to Google Drive, Dropbox, S3 & R2"
- Pro feature badge
- Providers table
- Connect steps
- Upload methods (direct, multipart, resumable)
- Upload history
- Managing connections

### features/video-library.mdx
**SEO:** "save video from website" (1.6K vol, diff 20)
- Title: "Video Library — Save & Organize Detected Videos"
- Saving videos (what's stored: title, thumbnail, link, hash)
- Library limits (free: 10, pro: unlimited)
- Accessing library at vidow.io/videos
- Dashboard overview at vidow.io/dashboard

- [ ] **Step 1: Rewrite all 6 feature pages**

Write each page from scratch. Every sentence original.

- [ ] **Step 2: Commit**

```bash
git add features/
git commit -m "docs: rewrite feature pages for Vidow with SEO optimization"
```

---

## Task 8: Video Tool Pages — NEW (7 pages)

**Files:**
- Create: `tools/video-compressor.mdx`
- Create: `tools/video-trimmer.mdx`
- Create: `tools/video-to-gif.mdx`
- Create: `tools/merge-videos.mdx`
- Create: `tools/add-audio.mdx`
- Create: `tools/hls-player.mdx`
- Create: `tools/cast-player.mdx`

Each tool page follows this structure:
1. Frontmatter with SEO title + description
2. 1-2 sentence intro with primary keyword
3. "How to [action]" with Steps component
4. Supported formats/options table
5. Free vs Professional availability
6. "All processing happens in your browser" trust signal (for conversion tools)
7. Related tools CardGroup

### tools/video-compressor.mdx
**SEO:** "video compressor" (90.5K vol, diff 65)
- Title: "Video Compressor — Reduce Video File Size in Your Browser"
- Explain compression options, quality vs size
- Supported input/output formats

### tools/video-trimmer.mdx
**SEO:** "video trimmer online"
- Title: "Video Trimmer — Cut & Trim Videos in Your Browser"
- Set start/end timestamps, preview, export

### tools/video-to-gif.mdx
**SEO:** "video to gif" (90.5K vol, diff 33)
- Title: "Video to GIF Converter — Create Animated GIFs from Video"
- Frame rate, dimensions, duration controls

### tools/merge-videos.mdx
**SEO:** "merge videos online"
- Title: "Merge Videos — Combine Multiple Video Files into One"
- Add files, reorder, format compatibility

### tools/add-audio.mdx
**SEO:** "add audio to video"
- Title: "Add Audio to Video — Replace or Overlay Audio Tracks"
- Replace existing audio, add background music

### tools/hls-player.mdx
**SEO:** "hls player online"
- Title: "HLS Player — Play M3U8 Streams in Your Browser"
- Paste m3u8 URL, quality selection, full playback controls

### tools/cast-player.mdx
**SEO:** "cast video to tv"
- Title: "Cast Player — Stream Videos to Chromecast & AirPlay"
- How it works with detected streams, session management, device selection

- [ ] **Step 1: Create all 7 tool pages**

Write each page from scratch following the template in the spec.

- [ ] **Step 2: Commit**

```bash
git add tools/
git commit -m "docs: add 7 video tool pages for Vidow"
```

---

## Task 9: Existing Download Guides (4 pages)

**Files:**
- Modify: `guides/download-hls-streams.mdx`
- Modify: `guides/download-from-vimeo.mdx`
- Modify: `guides/youtube-and-chrome-extensions.mdx`
- Modify: `guides/tips-and-tricks.mdx`

### guides/download-hls-streams.mdx
**SEO:** "m3u8 downloader" (2.4K vol, diff 18)
- Title: "M3U8 Downloader — How to Download HLS Streams with Vidow"
- Include "download hls stream", "m3u8 video downloader", "m3u8 downloader chrome", "m3u8 downloader online" naturally
- What is HLS, how to download (Steps), converting to MP4, live stream recording, separate audio/video, tips

### guides/download-from-vimeo.mdx
**SEO:** "download vimeo video" (33.1K vol, diff 25)
- Title: "Download Vimeo Videos — Enhanced Detection with Vidow"
- Vimeo-specific detection, progressive vs HLS, embedded players, quality table

### guides/youtube-and-chrome-extensions.mdx
- Title: "YouTube & Chrome Extensions — Why It Doesn't Work & What Does"
- CWS policy explanation, what Vidow CAN do, platform alternatives, legitimate YouTube offline options

### guides/tips-and-tricks.mdx
- Title: "Tips & Tricks — Get the Most Out of Vidow"
- Detection tips (SPA, play first, multiple videos), download tips, cloud tips, extension tips, billing tips

- [ ] **Step 1: Rewrite all 4 guide pages**

- [ ] **Step 2: Commit**

```bash
git add guides/download-hls-streams.mdx guides/download-from-vimeo.mdx guides/youtube-and-chrome-extensions.mdx guides/tips-and-tricks.mdx
git commit -m "docs: rewrite download guides for Vidow with SEO optimization"
```

---

## Task 10: Platform Download Guides — NEW (5 pages)

**Files:**
- Create: `guides/download-from-facebook.mdx`
- Create: `guides/download-from-instagram.mdx`
- Create: `guides/download-from-tiktok.mdx`
- Create: `guides/download-from-pinterest.mdx`
- Create: `guides/download-from-reddit.mdx`

Each follows the platform guide template from the spec:
1. Intro targeting "[platform] video downloader"
2. How Vidow detects videos on [Platform] (universal detection explanation — HLS/MP4)
3. Step-by-step download with platform-specific tips
4. Quality options table
5. Platform-specific tips section
6. FAQ AccordionGroup (3-4 questions)
7. Install CTA Card

### guides/download-from-facebook.mdx
**SEO:** "download facebook video" (90.5K vol, diff 18)
- Title: "Download Facebook Videos — Save FB Videos with Vidow"
- Tips: play video first, works on desktop site, public vs private video notes

### guides/download-from-instagram.mdx
**SEO:** "instagram video downloader" (368K vol, diff 36)
- Title: "Instagram Video Downloader — Download Reels, Stories & Posts"
- Tips: reels detection, stories (must play), embedded IG players

### guides/download-from-tiktok.mdx
**SEO:** "tiktok video downloader" (246K vol, diff 27)
- Title: "TikTok Video Downloader — Save TikTok Videos with Vidow"
- Tips: watermark-free detection when available, play video first

### guides/download-from-pinterest.mdx
**SEO:** "pinterest video downloader" (60.5K vol, diff 11)
- Title: "Pinterest Video Downloader — Download Pinterest Videos Easily"
- Tips: click into pin first, play the video

### guides/download-from-reddit.mdx
**SEO:** "reddit video downloader" (33.1K vol, diff 26)
- Title: "Reddit Video Downloader — Save Reddit Videos with Vidow"
- Tips: Reddit serves separate audio+video (Vidow auto-muxes), hosted vs embedded

- [ ] **Step 1: Create all 5 platform guide pages**

- [ ] **Step 2: Commit**

```bash
git add guides/download-from-facebook.mdx guides/download-from-instagram.mdx guides/download-from-tiktok.mdx guides/download-from-pinterest.mdx guides/download-from-reddit.mdx
git commit -m "docs: add 5 platform download guides for Vidow SEO"
```

---

## Task 11: Cloud Storage Setup Guides (4 pages)

**Files:**
- Modify: `guides/setup-google-drive.mdx`
- Modify: `guides/setup-dropbox.mdx`
- Modify: `guides/setup-aws-s3.mdx`
- Modify: `guides/setup-cloudflare-r2.mdx`

Each page:
- Title: "Set Up [Provider] — Cloud Video Storage with Vidow"
- All URLs use vidow.io (not savemate.io)
- Fresh wording for every section — same technical steps but different sentences
- Prerequisites, connect steps, how uploads work, managing connections, troubleshooting accordion

The AWS S3 page keeps the IAM policy JSON (that's AWS-specific, not SaveMate copy). The R2 comparison table stays (factual data). But all prose around them is rewritten.

- [ ] **Step 1: Rewrite all 4 cloud storage setup pages**

- [ ] **Step 2: Commit**

```bash
git add guides/setup-google-drive.mdx guides/setup-dropbox.mdx guides/setup-aws-s3.mdx guides/setup-cloudflare-r2.mdx
git commit -m "docs: rewrite cloud storage setup guides for Vidow"
```

---

## Task 12: Account Pages (3 pages)

**Files:**
- Modify: `account/registration.mdx`
- Modify: `account/settings.mdx`
- Modify: `account/security.mdx`

### account/registration.mdx
- Title: "Registration & Login — Create Your Vidow Account"
- All URLs → vidow.io/register, vidow.io/login
- Email registration steps, Google Sign-In, password reset
- Feature comparison table (with vs without account)
- Account deletion link → vidow.io/settings/profile

### account/settings.mdx
- Title: "Profile & Settings — Manage Your Vidow Account"
- URLs → vidow.io/settings/profile, vidow.io/settings/appearance
- Profile fields, email change flow, avatar, theme (light/dark/system), deletion

### account/security.mdx
- Title: "Security — Two-Factor Authentication & Session Management"
- URL → vidow.io/settings/security
- Password update, 2FA setup steps, signing in with 2FA, browser sessions, logout other sessions

- [ ] **Step 1: Rewrite all 3 account pages**

- [ ] **Step 2: Commit**

```bash
git add account/
git commit -m "docs: rewrite account pages for Vidow"
```

---

## Task 13: Billing Pages (3 pages)

**Files:**
- Modify: `billing/plans.mdx`
- Modify: `billing/lifetime.mdx`
- Modify: `billing/manage.mdx`

### billing/plans.mdx
**SEO:** "video downloader professional" (2.4K vol, diff 4)
- Title: "Plans & Pricing — Free vs Professional Video Downloader"
- Include "video downloader professional chrome extension" and "video downloader pro chrome extension" naturally
- Plan comparison table (fresh layout, same data)
- Billing options (monthly, yearly, lifetime) CardGroup
- Free plan details, Professional plan details
- Link to vidow.io/pricing

### billing/lifetime.mdx
- Title: "Lifetime Access — Pay Once, Download Forever"
- What's included, how it works (Steps), upgrading from subscription, FAQ accordion
- Link to vidow.io/pricing

### billing/manage.mdx
- Title: "Manage Subscription — Billing Dashboard"
- All URLs → vidow.io/billing
- Dashboard overview, plan changes, payment methods, invoices, coupons

- [ ] **Step 1: Rewrite all 3 billing pages**

- [ ] **Step 2: Commit**

```bash
git add billing/
git commit -m "docs: rewrite billing pages for Vidow with SEO keywords"
```

---

## Task 14: Support Pages (2 pages)

**Files:**
- Modify: `support/faq.mdx`
- Modify: `support/troubleshooting.mdx`

### support/faq.mdx
- Title: "FAQ — Frequently Asked Questions About Vidow"
- AccordionGroup sections: General, Downloads, Extension, Billing
- Do NOT claim "no data collected or tracked" — say "Vidow processes video detection locally in your browser. Limited data (page URLs for fallback detection, video metadata when you save) is sent to Vidow servers. See our [privacy page](/privacy) for full details."
- All URLs → vidow.io, CWS link uses Vidow ID

### support/troubleshooting.mdx
- Title: "Troubleshooting — Fix Common Vidow Issues"
- Sections: stream not detected, download fails, extension not in toolbar, cloud sync issues, account issues, download limit, cloud upload stuck, payment issues, SPA detection, report a bug
- All URLs → vidow.io
- Contact card → vidow.io/contact

- [ ] **Step 1: Rewrite both support pages**

- [ ] **Step 2: Commit**

```bash
git add support/
git commit -m "docs: rewrite support pages for Vidow"
```

---

## Task 15: Copyright & Fair Use Guide

**Files:**
- Modify: `guides/copyright-and-fair-use.mdx`

- Title: "Copyright & Fair Use — Your Responsibilities"
- Fresh wording for all sections — same legal concepts, different prose
- Fair use factors table, acceptable uses, cautionary scenarios
- Vidow's position section (accurate: detects unprotected streams, local processing, CWS compliant)
- DMCA contact → vidow.io/contact
- Best practices list

- [ ] **Step 1: Rewrite copyright page**

- [ ] **Step 2: Commit**

```bash
git add guides/copyright-and-fair-use.mdx
git commit -m "docs: rewrite copyright and fair use guide for Vidow"
```

---

## Task 16: Final Verification

- [ ] **Step 1: Search for any remaining "SaveMate" or "savemate.io" references**

```bash
grep -ri "savemate" --include="*.mdx" --include="*.json" .
```

Expected: zero results. If any found, fix them.

- [ ] **Step 2: Search for old extension ID**

```bash
grep -r "lejgkageoahacjmljeogapbkhbfldigd" --include="*.mdx" --include="*.json" .
```

Expected: zero results.

- [ ] **Step 3: Verify all internal links resolve**

Check that every `href="/..."` path in the MDX files corresponds to an actual file.

- [ ] **Step 4: Verify docs.json page list matches actual files**

Every page listed in docs.json navigation must have a corresponding .mdx file.

- [ ] **Step 5: Final commit**

```bash
git add -A
git commit -m "docs: verify Vidow rebrand complete — zero SaveMate references"
```
