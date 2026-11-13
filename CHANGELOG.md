# Changelog

> **Versioning note:** Starting with `0.3.0`, AniMac adopts pre-1.0 `0.x.y` Semantic Versioning (`CFBundleVersion` remains monotonically increasing from `3`). Prior tags `1.0.0` (build `1`) and `1.1.0` (build `2`) correspond to the initial `0.1.0` and `0.2.0` milestones.

## [Unreleased]

## [0.3.0] - 2026-11-13

- Switched to `0.x.y` pre-1.0 semantic versioning (`0.3.0`, build `3`), with epoch-aware `UpdateService.isVersion(_:newerThan:)` transition handling for legacy `1.0.0`/`1.1.0` releases.
- Transitioned to a proprietary closed-source distribution model (`All Rights Reserved`); public Universal 2 `.dmg` releases, SHA-256 checksums, and issue tracking are now hosted on [`warkurr/AniMac-Releases`](https://github.com/warkurr/AniMac-Releases).
- Added macOS menu bar companion (`MenuBarExtra`) with catch-up & upcoming airing tracker, quick `+1` episode progress, background lifecycle persistence, Dock visibility toggle, Launch at Login (`SMAppService`), and Liquid Glass window styling.
- Added configurable desktop episode airing notifications (`NotificationService`) and `animac://` deep-link routing.
- Hardened auto-updater verification, OAuth/deep-link handling, GraphQL variable parameterization, and build/release CI workflows.

> **Upgrading from legacy `1.0.0` / `1.1.0`:** Because `0.3.0` resets the marketing version below `1.1.0` and moves public releases to `warkurr/AniMac-Releases`, existing `1.1.0` installs should upgrade once via `brew upgrade --cask animac` (or `brew reinstall --cask warkurr/tap/animac`) or by downloading `AniMac.dmg` from [`warkurr/AniMac-Releases`](https://github.com/warkurr/AniMac-Releases/releases/latest). All future updates (`0.3.1+`) are then handled automatically in-app.

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
