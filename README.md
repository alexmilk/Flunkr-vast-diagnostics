# Flunkr - VAST/VPAID Diagnostics Tool

A standalone web-based diagnostic tool for analyzing VAST/VPAID video ad tag performance. Built for ad ops and engineering teams investigating ad load issues, slow creatives, and broken tags.

## Features

### Input Methods
- **Tag URL** — paste a VAST ad tag URL and fetch it directly
- **Paste XML** — paste raw VAST XML to bypass CORS restrictions

### Performance Analysis
- **VAST Fetch Timing** — measures time-to-first-byte and total download time for the initial tag request
- **Wrapper Chain Resolution** — automatically follows VAST wrapper redirects (up to 10 levels deep), timing each hop individually
- **Media File Probing** — downloads the first 256KB of each media file to measure TTFB, download speed, and reports file size, bitrate, resolution, and codec
- **Tracking Pixel Testing** — fires all tracking URLs (impressions, quartiles, click tracking) and measures response times
- **Companion Ad Testing** — optionally tests companion ad resource loads (images, iframes)

### Visualization
- **Summary Cards** — at-a-glance metrics: total fetch time, wrapper depth, media file count, average media TTFB, slowest resource, and ad duration
- **Waterfall Chart** — visual timeline showing all resource loads with color-coded bars (fetch, media, tracking)
- **Wrapper Chain View** — step-by-step breakdown of each redirect with URL, timing, TTFB, and size
- **Media Files Table** — detailed table with URL, type, resolution, bitrate, size, TTFB, download time, status, and a copy-to-clipboard button for each URL
- **Tracking Events Table** — event type, URL, and response time for each tracking pixel
- **Companion Ads Table** — size, type, URL, timing, and status for each companion resource
- **VAST Structure Overview** — parsed tree view of all ads showing ad system, title, duration, click-through URL, and resource counts

### Ad Preview Players
- **Direct Player** — HTML5 video player that loads media files directly, with rendition selector (switch between quality levels) and real-time playback event log (loadstart, canplay, canplaythrough, stalled, error, etc.)
- **IMA SDK Player** — Google IMA SDK-based player that renders the ad exactly as a publisher's player would, including VPAID/SIMID execution, ad verification scripts, and viewability measurement. Logs full IMA lifecycle events (ADS_MANAGER_LOADED, LOADED, STARTED, FIRST_QUARTILE, MIDPOINT, THIRD_QUARTILE, COMPLETE, AD_BUFFERING, etc.) with timestamps and ad metadata

### Configurable Options
- Follow wrapper chains (on/off)
- Test media file downloads (on/off)
- Test tracking pixels (on/off)
- Test companion ads (on/off)

## Usage

Open `index.html` in a browser. No build step or dependencies required (IMA SDK is loaded from Google's CDN).

```bash
open index.html
```

**CORS Note:** Many ad servers block cross-origin browser requests. If you hit CORS errors with a tag URL, either paste the VAST XML directly (curl the URL from terminal) or use a local CORS proxy.

## Tech Stack

Single HTML file — vanilla HTML, CSS, and JavaScript. No frameworks or build tools. Google IMA SDK loaded via CDN for the IMA player mode.
