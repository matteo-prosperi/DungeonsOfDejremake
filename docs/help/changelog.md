# Changelog

All notable changes to **Dungeons of Dej'remake** are recorded here.

The format is based on [Keep a Changelog](https://keepachangelog.com/), and this
project uses git-height–based versioning (clean `0.1.x` releases on `main`).

[Back to Help index](index.md)

## [Unreleased]

Changes landed since 0.1.55 will be listed here until the next release is cut.

## [0.1.55] — 2026-09-14 — current release

Accurate ownership attribution and release-version reporting.

### Changed
- The game’s About dialog now displays the version stamped into each release
  build from the project’s git-derived release version.
- Legal notices now identify Decklin's Domain as the current owner of the
  _Mordor: The Depths of Dejenol_ IP and related games. _Depths of Dejenol_ and
  _Darkness Awakening_ are attributed as Decklin's Domain Ltd. trademarks.

### Fixed
- The release build now verifies that the Godot project version used by the
  About dialog exactly matches the git-derived release version before export.

## [0.1.54] — 2026-09-14

More reliable dungeon navigation, clearer town item lists, and better Seer
guidance.

### Changed
- The Bank’s stored-item list now uses the same class-based headings and
  alphabetical item order as the General Store.
- In both the Bank and General Store, equipped items appear beneath their
  individual equipment-slot heading; backpack items appear under
  **Unequipped Inventory**.
- After a successful Seer monster search, entering a room that can spawn the
  target now rolls a direct encounter chance before ordinary monster-type
  selection. Misses raise that chance from 20% to 40%, 60%, then 80%.

### Fixed
- Face-marker squares now show the player facing the forced direction both
  while lost and when the map is rotated normally.
- Cursed miscellaneous loot that must attach itself—such as Ball and Chain—now
  attaches and applies its effects immediately, as in the original game.
- The Seer no longer recommends an item carrier when that monster cannot
  generate a chest capable of producing the requested item.
- Recruited-ally status icons now use the Godot 4.7 RichTextLabel image-unit
  API and no longer prevent the dungeon scene from loading.
- Data validation now reports missing map data explicitly instead of failing
  while examining a linked teleporter or chute.

## [0.1.46] — 2026-09-10

Clearer teleporter map knowledge.

### Changed
- A teleporter confirmed random by use now appears bright green in the dungeon
  and Library maps. Purple remains an unknown destination type; cyan remains a
  used fixed teleporter. The green state is shared across characters and does
  not apply when co-op temporarily converts a fixed teleporter into a random
  relocation.
- Library teleporter destination-cell highlights are now cyan, matching the
  used fixed-teleporter glyph rather than using the player/map-selection yellow.

## [0.1.44] — 2026-09-10

Remembered teleporter destinations, clearer map edges, and more reliable
stolen-gold recovery and automatic buffs.

### Added
- Fixed teleporters used while the source position and floor are known now
  appear cyan in the dungeon and Library maps. Knowledge is shared across all
  characters; random teleporters and unrecorded uses retain their usual color.
- When a fixed teleporter's arrival position and floor are known, the Library
  remembers its immediate destination. Click/tap the source, or use
  keyboard/gamepad navigation, to select the destination floor and highlight
  its cell. Facing loss alone does not prevent learning, and later lost arrivals
  do not erase learned destinations. Older saves remain compatible and start
  with no recorded teleporter history.

### Fixed
- Map edges containing both a wall and an ordinary door now display as walls,
  matching their blocked movement behavior. Genuine discovered secret doors
  retain their wall-and-door appearance.
- Recoverable stolen gold is added after treasure scaling, rather than being
  multiplied with ordinary treasure. Recovery is reported when the gold is
  paid out, using the original game's message wording.
- Missing auto-enabled buffs are retried after a Blackout trap and after combat
  ends safely. Active buffs are not cast again, and escaping into another
  hostile encounter does not trigger casts between the two combats.

## [0.1.38] — 2026-09-07

More reliable touch scrolling in spell lists.

### Fixed
- The enlarged button-text preview no longer remains stuck on screen when
  touch-scrolling the dungeon or character spell lists. Starting a scroll
  dismisses the preview, including gestures that begin between spell rows.

## [0.1.37] — 2026-09-07

More reliable cloud-save history across devices, safer touch scrolling, and
clearer item details.

### Added
- Completely identified items now show their special-effect summary in item
  details: stat modification or restoration of 50 or 200 spell points, as
  appropriate.

### Changed
- Cloud saves now track each file's history across devices. A version that
  incorporates all changes from the other version is selected automatically,
  even when different devices last saved them. Independent edits and deletion
  conflicts still require review; older cloud-save formats remain readable.
- Explicit cloud conflict choices record both histories and the chosen content,
  helping prevent the same content conflict from reappearing. This does not
  merge character or world gameplay data.

### Fixed
- Offline save edits now retain their inherited cloud history and persist a new
  revision before synchronization; retries reuse the revision for unchanged
  content. Cloud-state recovery is also more robust after interrupted writes.
- Dragging a touch-scrollable list no longer activates the button where the
  gesture began, preventing accidental spell casts while scrolling.
- Hennart's monster portrait no longer has letterboxing and is properly framed
  at full square resolution.

## [0.1.33] — 2026-09-06

Faster and less intrusive cloud saves, more reliable input hints, and several
dungeon and ally-behavior corrections.

### Changed
- Cloud save objects are now gzip-compressed independently and small files use
  one-request multipart uploads, substantially reducing synchronization time
  while retaining compatibility with older uncompressed manifests.
- Cloud manifests now record a per-installation writer identity and monotonic
  revision. When both variants came from the same installation, the newer
  revision is selected automatically instead of showing an unnecessary
  conflict-choice screen.
- An ally's decision to cast **Charm of Opening** now depends on spell
  availability, its enabled setting, and SP cost—not thieving competency.
  Choosing the best character to physically open the unlocked chest remains a
  separate decision made after either the player or ally casts the spell.

### Fixed
- While lost, walking into a wall no longer marks the unseen cell beyond that
  wall as discovered.
- Touch-only Android devices no longer show keyboard key-cap hints. Connecting
  and using a physical keyboard still enables them.
- The Z/X/C/V hints on monster-group buttons no longer blink between combat
  refreshes. The four rows, target dots, and glyphs now remain mounted while
  their labels and group bindings update in place.

## [0.1.27] — 2026-08-16

Guild Hall touch reliability and clearer action availability.

### Changed
- Item details now show an item's `(g)`, `(n)`, or `(e)` alignment marker in
  red when it is opposed to the current character and would become cursed when
  equipped.
- Quest forfeiture now requires an explicit confirmation that explains the
  accumulated XP progress and guild levels that will be lost.

### Fixed
- On Windows touchscreens, the enlarged button-text preview no longer remains
  stuck on screen after pressing **Make Level**.
- Rebuilding the Guild Hall action area after **Re-Acquaint** can no longer
  reuse the same touch contact to activate the replacement action or dismiss
  its result dialog.
- **Make Level** remains visible but disabled when the character has enough XP
  but cannot afford the fee, with the missing-gold reason shown beside it.
- **Join**, **Re-Acquaint**, and pinned-quest **Forfeit Quest** actions remain
  visible but disabled while cursed equipment blocks them, with an explanation
  telling the player to remove the cursed items.
- A cursed-item-blocked guild join no longer moves gold out of the bank before
  failing.

## [0.1.26] — 2026-08-11

Cloud-save interoperability and startup usability fixes for Windows and
Android.

### Added
- The main menu now shows a prominent animated status panel while cloud saves
  are being checked. It replaces the game-start buttons temporarily rather than
  extending the menu over the title artwork.

### Changed
- Windows and Android now use OAuth clients from the same Google Cloud project,
  allowing both platforms to see the same hidden Google Drive save data.
- Startup cloud checks are faster: manifest metadata returned by Drive is
  reused, and orphan-file maintenance is deferred until a manual sync or save
  publish.
- Google Drive manifest concurrency now uses Drive file versions and
  copy-on-write replacement, matching the behavior supported by Drive API v3.

### Fixed
- Cloud saves downloaded on a new Windows installation now refresh the main
  menu and enable Continue and Load Character correctly.
- Legacy combined-format save files no longer obscure valid split character and
  world saves after migration.
- Running without Google Drive authorization or network access no longer traps
  the player at the startup gate; local offline play remains available.
- Fixed a startup crash caused by endlessly rescheduling cloud publishing when
  authentication was unavailable.
- Fixed manifest-read races and preserved the replacement manifest's Drive
  version during duplicate reconciliation.

## [0.1.20] — 2026-08-09

Cloud saves and expanded signed release builds for Windows and Android.

### Added
- **Google Drive cloud saves** now use the private `appDataFolder`, sharing save
  data across Windows and Android. Files sync individually through an
  ETag-protected manifest, with conflict resolution, migration backups, and
  conservative cleanup of orphaned files.
- Windows OAuth uses **PKCE**, with refresh tokens protected by **DPAPI**;
  Android authorization uses **Google Identity**.
- Windows releases now include both **x86-64 and ARM64** builds, and Android
  releases include a **release-signed APK**.
- OAuth and signing credentials can be carried between repository checkouts in
  a repository-portable release vault encrypted with **AES-256-GCM**.

## [0.1.17] — 2026-07-27

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
