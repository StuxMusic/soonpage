# Changelog

All notable changes to Soonpage are documented here.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/) (MAJOR.MINOR.PATCH).

## v1.0.4

### Added
- `.gitignore` for OS/editor cruft, local `.env` overrides, and `node_modules/`

### Changed
- Changelog badges now use the fixed shared palette — Added green, Changed blue, Fixed orange, Removed red, Security purple, Deprecated grey — as tinted pills, with darker variants in light mode
- `###` sections within each release are sorted into that same fixed order (Added, Changed, Fixed, Removed, Security, Deprecated) at render time, whatever order `CHANGELOG.md` lists them in; unknown types go last

## v1.0.3

### Fixed
- The footer's changelog/version link (and other footer links) turned accent-purple once visited — `a:visited` carries a pseudo-class, giving it higher CSS specificity than the plain `footer a` selector meant to keep footer links muted, so it kept winning regardless of source order. Every affected footer link now also styles `footer a:visited` explicitly.

## v1.0.2

### Fixed
- GitHub Pages was using the legacy branch-deploy build system, which can silently stop auto-deploying with no error recorded anywhere (discovered on SeasonalOverlaysLibrary — its live site served stale content for over an hour with no visible failure). Switched to GitHub Actions-based Pages deployment (`.github/workflows/pages.yml`), making every deploy an ordinary, observable CI run instead.

## v1.0.1

### Changed

- Tagline now clarifies this page is reused for an individual artist page and/or the main Stux.Music website, not just the platform itself

## v1.0.0

### Added

- Initial release: self-hosted Font Awesome (solid icons, matching Stux.Music's
  actual design), a "Boring Legal Stuff" legal hub (`legal.html` + `legal/`),
  `changelog.html` that fetches and renders `CHANGELOG.md` at runtime, a
  version indicator fetched live from `VERSION.md`, cross-origin
  `postMessage` title sync, `dev-server.sh` / `dev-server.bat`, and a custom
  `404.html` error page
