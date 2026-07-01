# Changelog

All notable changes to **Dungeons of Dej'remake** are recorded here.

The format is based on [Keep a Changelog](https://keepachangelog.com/), and this
project uses git-height–based versioning (clean `0.1.x` releases on `main`).

[Back to Help index](index.md)

## [Unreleased]

Changes landed since 0.1.9 will be listed here until the next release is cut.

## [0.1.9] — 2026-06-30 — current release

### Added
- Player help & guide: a per-screen how-to set under `docs/help/`, with a
  Quickstart, a per-page "differences from the original" section, and this
  changelog. Linked from the project README.
- Guild Hall details now show, for each guild: the HP gained per level
  ("Grants X HP until level Y, Z HP after level Y"), how likely the guild is to
  assign a quest as a level-up requirement, and its XP requirement normalized to
  Nomad (Nomad = 100%, e.g. Warrior 200%).
- Main menu **Help** button that opens the online Player Help & Guide
  (this GitHub Pages site) in your browser.

### Changed
- Character creation now shows each race's XP cost as a "XP Penalty: N%"
  relative to Human (the fastest learner) instead of the raw experience
  multiplier — Human 0%, Morloch 6%, … Troll 26%.
- The dungeon combat log now groups related messages for the same
  actor/round onto a single wrapped line — a character's attack swings, a
  round of monster attacks, companion actions, a chest's contents, and
  "Victory!" plus its gold — making better use of the limited log height.

### Fixed
- Monsters that turn hostile via the per-tick aggression roll now get their
  faithful free opening strike on that tick (the party's first action is skipped
  that round), matching the original game.
- Removed a duplicated "You walk away." message that could appear when leaving
  a fight.

## [0.1.3]

Baseline for this changelog. Earlier history is not itemized here; tracking
starts from this release going forward.
