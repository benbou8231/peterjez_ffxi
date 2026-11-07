# Changelog

All notable changes to this DigTracker fork are documented in this file.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and version numbers follow [Semantic Versioning](https://semver.org/)
(`MAJOR.MINOR.PATCH`): PATCH for fixes, MINOR for new backward-compatible
features, MAJOR for breaking changes.

Original project: [peterjez/ffxi](https://github.com/peterjez/ffxi)

## [3.5.0] Track successful digs per skill-up interval

### Added

- Track successful digs since the last skill-up across sessions.
- Store successful-dig counts in historical skill-up records.
- Display the last three successful-dig counts alongside recent intervals.

### Changed

- Migrate existing skill-up history with zero placeholders for unavailable success counts.
- Display `N/A` for unknown or potentially incomplete success intervals.

### Compatibility

- Preserve existing character statistics and dig history without requiring manual migration.

## [3.4.0] Improve skill-up interval statistics

### Changed

- Replace lifetime average and Best/Worst statistics with a rolling average of the last five completed skill-up intervals and the last three intervals (oldest to newest).
- Replace DUE/Below Avg status with the number of digs above or below the rounded rolling average.
- Add fork maintainer attribution to the addon metadata while preserving original author credit.

### Compatibility

- Preserve existing character data and persistent skill-up history without migration.

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
