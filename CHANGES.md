# Flunkr - Changes Log

## May 11, 2026
- **NEW** Added gear icon to header title
- **NEW** Added BETA badge to header
- **NEW** Added Changes Log dialog and CHANGES.md file
- **REMOVED** Geo Map view from Tracking Domain Map — endpoint locations could not be reliably resolved (most ad-tech traffic terminates at CDN edges, making the markers misleading)
- **IMPROVED** Tracking Domain Map radial view — domain nodes are now donut charts whose arc segments show the per-domain event-type breakdown (3rd visual aspect alongside ring distance and node size); added curved category-colored links, glow-lit core, guide rings, and inline domain labels

## April 20, 2026
- **NEW** Initial release of Flunkr - VAST/VPAID Diagnostics Tool
- **NEW** VAST tag URL input with fetch timing and TTFB measurement
- **NEW** Paste XML input mode to bypass CORS restrictions
- **NEW** Wrapper chain resolution — follows up to 10 redirect levels with per-hop timing
- **NEW** Media file probing — downloads first 256KB, reports TTFB, size, bitrate, resolution
- **NEW** Tracking pixel testing — fires all tracking URLs and measures response times
- **NEW** Companion ad testing (optional)
- **NEW** Summary cards — VAST fetch, wrapper depth, media files, avg TTFB, slowest resource, duration
- **NEW** Waterfall chart — visual timeline of all resource loads
- **NEW** VAST structure overview — parsed tree of all ads with metadata
- **NEW** Copyright footer
- **NEW** Direct HTML5 video player with rendition selector and playback event log
- **NEW** IMA SDK player — realistic ad playback with full IMA lifecycle event logging
- **CHANGED** IMA SDK player set as the default player mode
- **NEW** Copy-to-clipboard button on media file URLs
- **IMPROVED** Enlarged IMA SDK player container (800px, 16:9 aspect ratio)
- **NEW** Tracking Domain Map — radial SVG diagram showing all third-party domain connections with domain summary table
- **NEW** VPAID/SIMID detection summary card
- **NEW** README.md documentation
- **CHANGED** Renamed tool to Flunkr - VAST/VPAID Diagnostics Tool
