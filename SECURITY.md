# Security policy

## Supported versions

| Version | Supported          |
| ------- | ------------------ |
| 0.3.x   | :white_check_mark: |
| <= 1.1.0 (legacy) | :x:       |

## Security & privacy model

- **Direct API communication**: AniMac communicates exclusively over HTTPS with the official AniList GraphQL API (`https://graphql.anilist.co`) and AniList CDN (`https://s4.anilist.co`). No intermediate servers or third-party analytics are used.
- **Local token storage**: Your AniList OAuth 2.0 access token is stored locally inside your user-scoped `~/Library/Application Support/AniMac/` directory (`0700` directory permissions, `0600` owner-only file permissions) so macOS does not prompt for Keychain access on every unsigned/ad-hoc build update. It never leaves your Mac except to authenticate requests to AniList.
- **Minimal entitlements**: The application bundle only requests `com.apple.security.network.client`.

## Reporting a vulnerability

If you discover a security vulnerability in AniMac, please report it privately via [GitHub Security Advisories](https://github.com/warkurr/AniMac/security/advisories/new) rather than opening a public issue.
