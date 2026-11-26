# Changelog

> **Versioning note:** Starting with `0.3.0`, AniMac adopts pre-1.0 `0.x.y` Semantic Versioning (`CFBundleVersion` remains monotonically increasing from `3`). Prior tags `1.0.0` (build `1`) and `1.1.0` (build `2`) correspond to the initial `0.1.0` and `0.2.0` milestones.

## [Unreleased]

## [0.4.2] - 2026-11-26

- Added native macOS **Spotlight** library indexing (`SpotlightIndexService`, `CoreSpotlight`) with interactive `.animac` Quick Look preview cards (`AniMacQuickLook.appex`) supporting cover thumbnails, progress bars, `+1` episode/chapter quick increment via `animac://increment/<id>`, and Space/Escape keyboard dismissal. Strictly excludes `18+`, private entries, and Demo Mode.
- Fixed keyboard navigation shortcuts (`⌘2` / `⌘3`) and `animac://library/...` deep links when *All Anime* / *All Manga* are hidden by default, plus `⌘R` refresh state handling.
- Fixed `isPrivate` preservation across saves and detail views, zero-count normalization (`episodes == 0` / `chapters == 0` / `volumes == 0`), missing studios and synonyms in library/discovery/search queries, manga release-year sorting, and stale caught-up items in the Menu Bar schedule.
- Improved **Media Detail**, **Global Search** (pagination for Characters & Staff, aligned grids), **Library** (search across native titles and synonyms, O(1) lookup indexes, deterministic sort tie-breakers), **Statistics**, disk image cache fast-path, and off-main-actor DMG update streaming.

## [0.4.1] - 2026-11-23

- Added country-specific legal streaming availability (**Where to Watch**) on anime detail pages via JustWatch GraphQL and AniList `externalLinks`, with automatic macOS country detection and country selectors in **Settings → Appearance** and on detail pages.
- Redesigned personal media tracking into a minimalist inline bar inside the hero banner (`BannerTrackingBar`), removing the standalone Tracking card and reordering detail sections (**Synopsis → Information → Where to Watch**).
- Added clickable full-window poster lightbox preview with native macOS in-window blur (`NSVisualEffectView`) and proportional rounded corners.
- Made the Menu Bar popover dynamically adapt its height to fit 0–4 airing items without empty space below, scrolling vertically beyond 4 items.
- Added a discreet localized Ko-fi support badge in **Settings → About**.

## [0.4.0] - 2026-11-17

- Added full native localization across **7 languages**: English (`en`), French (`fr`), Spanish (`es`), European Portuguese (`pt-PT`), Dutch (`nl`), German (`de`), and Italian (`it`), complete with pluralization rules (`Localizable.stringsdict`), localized AniList tag catalog (`TagCatalog.strings`), and instant restart-free language switching in **Settings → Appearance**.
- Simplified **Settings → About & Updates** by removing redundant GitHub Releases links and explanatory subtitles.
- Added `description(asHtml: false)` to Discovery list queries so the Home Hero Banner displays the full media synopsis.
- Fixed a SwiftUI/AppKit `NSOutlineView` selection double-label rendering artifact in the sidebar on macOS.
- Expanded the GitHub showcase gallery to 8 Retina screenshots covering Light and Dark modes, the Menu Bar Companion, Personal Statistics, and Settings.

## [0.3.1] - 2026-11-14

- Removed macOS Keychain (`login.keychain-db`) reads/writes in `KeychainService` so locally signed or ad-hoc release updates no longer trigger system Keychain password prompts after binary rebuilds.
- Preserved AES-256-GCM local vault encryption (`~/Library/Application Support/AniMac/.vault_key` and `.session_vault`) with `0700`/`0600` POSIX permissions, symlink guards, atomic writes, and silent cleanup of legacy Keychain entries.

## [0.3.0] - 2026-11-13

- Switched to `0.x.y` pre-1.0 semantic versioning (`0.3.0`, build `3`), with epoch-aware `UpdateService.isVersion(_:newerThan:)` transition handling for legacy `1.0.0`/`1.1.0` releases.
- Transitioned to a proprietary closed-source distribution model (`All Rights Reserved`); source code is hosted privately (`warkurr/AniMac-Source`), while public Universal 2 `.dmg` releases, SHA-256 checksums, and issue tracking are hosted on [`warkurr/AniMac`](https://github.com/warkurr/AniMac).
- Added macOS menu bar companion (`MenuBarExtra`) with catch-up & upcoming airing tracker, quick `+1` episode progress, background lifecycle persistence, Dock visibility toggle, Launch at Login (`SMAppService`), and Liquid Glass window styling.
- Added configurable desktop episode airing notifications (`NotificationService`) and `animac://` deep-link routing.
- Hardened auto-updater verification, OAuth/deep-link handling, GraphQL variable parameterization, and build/release CI workflows.

> **Upgrading from legacy `1.0.0` / `1.1.0`:** Because `0.3.0` resets the marketing version below `1.1.0`, existing `1.1.0` installs should upgrade once via `brew upgrade --cask animac` (or `brew reinstall --cask warkurr/tap/animac`) or by downloading `AniMac.dmg` from [`warkurr/AniMac`](https://github.com/warkurr/AniMac/releases/latest). All future updates (`0.3.1+`) are then handled automatically in-app.

## [1.1.0] - 2026-11-12

- In-app automatic update checker and one-click `.dmg` installer (via GitHub Releases).
- Expanded Demo Mode with 16 anime, 8 manga, and full statistics preview.
- Styled `.dmg` installer window with drag-to-Applications layout.
- Modularized global search architecture and unified English diagnostic logs.
- Switched license to GNU GPL v3.0 and updated bundle identifier to `com.warkurr.animac` with automatic cache migration.

## [1.0.0] - 2026-11-11

- Initial release of AniMac for macOS 14.0+ (Universal 2: `arm64` & `x86_64`).
- Anime and manga library sync with AniList, grid/table views, and optimistic `+1` progress updates.
- Discovery dashboard (trending, seasonal, upcoming, top rated).
- Global search across anime, manga, characters, and staff with genre and tag filtering.
- Personal statistics dashboard and customizable sidebar.
- English and French localization with automatic system language detection.
