# Changelog

All notable changes to this DigTracker fork are documented in this file.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and version numbers follow [Semantic Versioning](https://semver.org/)
(`MAJOR.MINOR.PATCH`): PATCH for fixes, MINOR for new backward-compatible
features, MAJOR for breaking changes.

Original project: [peterjez/ffxi](https://github.com/peterjez/ffxi)

## [3.3.1] Sort looted items alphabetically

### Fixed

- Display looted items alphabetically in the session HUD instead of relying
  on Lua's unpredictable table iteration order.
- Save persistent item records alphabetically for consistent ordering
  across characters and sessions, without changing item counts.

## [3.3.0] Add regional currency tracking

### Added

- Track Conquest Points, Imperial Standing, Allied Notes, and Bayld separately.
- Display session and lifetime totals for each currency, including multiple
  currencies collected across different regions during the same session.

### Changed

- Preserve previously recorded Conquest Points when migrating existing
  character data to the new regional currency structure.

## [3.2.1] Restrict digging tracking to chocobo

### Fixed

- Only process digging messages while riding a chocobo (`status == 5`),
  preventing unrelated messages from being counted while on foot.

*Version assigned retroactively; the addon version was not changed at the time.*

## [3.2] Fork original DigTracker

- Forked the original DigTracker project by peterjez without functional changes.
