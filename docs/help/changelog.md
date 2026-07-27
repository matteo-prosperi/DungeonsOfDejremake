# Changelog

All notable changes to **Dungeons of Dej'remake** are recorded here.

The format is based on [Keep a Changelog](https://keepachangelog.com/), and this
project uses git-height–based versioning (clean `0.1.x` releases on `main`).

[Back to Help index](index.md)

## [Unreleased]

Changes landed since 0.1.17 will be listed here until the next release is cut.

## [0.1.17] — 2026-07-27 — current release

An engine upgrade plus a round of combat-readability polish: things that take
damage now visibly react.

### Added
- Taking damage now **shakes** the thing that was hit. Alongside your own status
  bar, this now covers your **ally line**, each **companion entry**, and each
  **monster group** in the encounter panel — each one reacting to its own
  damage, so you can see at a glance which group your attack actually landed on.
  The strength of the shake scales with how hard the hit was and how close to
  death the target is. In co-op both players' panels react independently.

### Changed
- The game now runs on **Godot 4.7.1** (up from 4.6.2).
- Ally affliction icons now **scale with the interface font** instead of staying
  a fixed size, so they stay legible when the UI is scaled up on phones and TVs.
- A gamepad can no longer drive your character while the **game window is not
  focused**.
- On Android the **Godot boot splash is gone** — the system splash stays up
  until the game is ready, so startup no longer shows two splash screens.

### Fixed
- Corrected the alignment of **friendly-monster group portraits** when the peace
  sign is shown: with a single group the portrait now sits exactly where it does
  in a fight, with the peace sign to its right, instead of being pushed off
  center. (With three groups the whole block stays centered — there is no room
  for the peace sign to hang off the side.)
- Keyboard key-cap hints on the **monster group buttons** no longer flicker in
  the wrong place between turns.

## [0.1.12] — 2026-07-13

A large playtest pass (dungeon levels 1–4): 20 fixes plus 5 new ally-focused
features.

### Added
- **Healer/Sorcerer** (and Sorcerer/Healer) is now a valid recruited-ally guild
  combination — an ally that can both heal and cast resistances.
- Allies with **defensive casting** enabled now cast their **Resist** spells on
  you and on each other before and during fights.
- A new ally command to **force a recruited ally to cast Charm of Opening** on
  the current locked chest (they still cast it automatically when it's cheap).
- **Per-spell checkboxes** in the ally spell list (Character screen) to stop an
  ally from casting a specific spell.
- Recruited allies now **help identify** monsters and items — identification uses
  the best identifier among you and your living allies.
- The character screen now shows your **actual current number of combat swings**
  alongside the guild competency ratings.
- A **gamepad binding** for the "remove cursed item" action.
- In the store's buy list, **left/right (d-pad)** now jumps to the previous/next
  item category.

### Changed
- **Guild Abilities** are now shown as percentages (`n%`) on the character
  screen, tavern cards, ally details, and the Hall of Fame mastery records.
- The ally command menu is now a **single list** — Charm of Opening at the top
  (only when a locked chest is present and the ally can afford it), then every
  heal/cure/buff you can cast on that ally — titled by the ally's name. Spells
  you can't currently cast are **hidden** instead of shown greyed out.
- The Guild Hall HP line now names the CON bonus and reads
  "Grants X HP + CON bonus until level Y, then Z HP".
- The Guild Hall no longer lists ratings of 0.
- **Drained ally** stats (and the guild access that depends on them) are now
  restored on town entry, just like the player's — allies no longer lose spells
  or their secondary guild after being drained.
- Recruited allies can **never lose guild levels** when their experience is
  updated.

### Fixed
- No longer **dying right after taking the stairs** — a stale pending encounter
  from the previous level could act against your just-arrived character.
- Corrected the **horizontal alignment** of friendly-monster group portraits.
- Action and hotbar buttons are now **disabled for spells you can't currently
  cast** (for example, stats too low) instead of failing after you click them.
- The **Forfeit Quest** button now appears — and is labeled "Forfeit Quest"
  rather than "Make Level" — when you're at the level cap with a pending quest.
- The forfeit dialog no longer shows literal `%s` placeholders.
- **Hall of Fame** stat and HP records keep updating when the same holder
  improves past their own previous record.
- An ally with no usable weapon now **defends** instead of making an ineffective
  empty-handed attack; gear unequipped because of low stats is re-equipped on
  town entry.
- Keyboard and mouse hints only appear after a keyboard or mouse is actually
  used — phones no longer show them by default.
- Popup buttons are now **large enough to tap** in mobile and touch modes.
- Items you **sell to the store** now always appear in the Library.
- The Library now says a creature was last seen on **"Level N"** instead of a
  bare number.

## [0.1.10] — 2026-06-30

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
