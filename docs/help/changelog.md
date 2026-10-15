# Changelog

All notable changes to **Dungeons of Dej'remake** are recorded here.

The format is based on [Keep a Changelog](https://keepachangelog.com/), and this
project uses git-height–based versioning (clean `0.1.x` releases on `main`).

[Back to Help index](index.md)

## [Unreleased]

No changes yet.

## [0.1.74] — 2026-10-15 — current release

Consistent switches, shared buff automation, and smoother local saving.

### Added
- A dedicated **Buffs** master and per-spell **Self / All / Disabled** modes
  for played characters and allies. Healing and cures remain separate.
- Confirmation dialogs before dismissing a character, attacking a companion,
  or kicking a companion out of the party.

### Changed
- Binary settings use one bordered control containing both their label and
  switch indicator, including settings, ally capabilities, movement lock,
  original-asset preferences, and keyboard Caps.
- Active characters in the same dungeon room share out-of-combat buff support,
  including both co-op parties when together. Urgent ally support goes first;
  useful cheaper mass casts precede self-casts, followed by the cheapest
  eligible **All** helper. Buffs use exact affordability without a healing-SP
  reserve, so automatic buffing can spend all available SP.
- Existing AI-enabled buffs migrate to **All**, even if their old Auto checkbox
  was off. Explicit new modes are preserved when saving and switching control.
- Automatic human combat defaults choose **Attack** when enabled, otherwise
  **Tank** when enabled, otherwise **Defend**. Manually selected stances remain
  in effect during the encounter.
- Local party/world saves run in the background to reduce pauses during
  movement, town visits, and sales. Pending saves coalesce to the latest state;
  coherent checkpoints and recovery protection are retained.
- Tavern cards scroll horizontally and show every saved character's guild
  levels, including an active guild at level zero.
- Store sale lists and receipts show the item's gross offer consistently;
  actual party sharing and ally expenses are unchanged.

### Fixed
- Leaving the game, switching apps, and Android Back flush the latest local
  save without waiting for a cloud upload.
- Ally capability and spell-mode changes preserve menu controls, scroll
  position, and focus instead of jumping back to the top.
- Mass Levitate, Mass Sight Veil, and Mass Protection affect eligible party
  characters, not charmed monsters, matching the original game. Automatic
  casting no longer spends SP solely for ineffective companion buff entries.
- Characters on different cells of a valid area-zero room can share buffs.
  Characters in other rooms or on other floors remain excluded.
- An already-buffed character can use a mass-buff item to help an unbuffed
  character in the actual participating party.
- Mobile slide-to-activate gestures toggle Caps and ally-menu switches
  correctly without double-activating ordinary taps.
- Compact spell lists retain readable names, aligned SP costs, and accessible
  buff controls without shrinking fonts.

## [0.1.71] — 2026-10-14

Recruit your own characters, build larger solo parties, and switch control
without leaving the dungeon.

### Added
- Other saved characters with compatible alignments appear in the Tavern,
  with their equipment shown alongside their character details. Hire them
  without a generated ally's recruitment fee.
- Single-player parties support up to three allies and eight monster
  companions. Each co-op player can hire one ally and keep four monsters.
- Expanded solo parties use a scrollable left sidebar for allies and companions.
- Switch control to a living, active saved party member in town or the dungeon.
  The character keeps their own equipment, progression, inventory, and bank;
  the original character remains the party's save anchor.
- Town party exchange supports items and bank gold between real characters,
  with an amount scroller capped at the sender's bank balance.

### Changed
- Saved recruits use the existing ally AI while retaining their own character
  progression. Their personal companion rosters remain inactive while hired.
- Party members and monsters exceeding the current mode's limits are parked
  rather than discarded, with reunion and dismissal support.
- Dungeon income is shared among eligible participants in the encounter;
  shared town sales credit the appropriate characters' banks.
- Monster kills by any party member or companion count toward the involved
  party members' monster quests.
- Canonical party members and the shared world are saved together through a
  recoverable local or cloud transaction. Newer or incompatible save data is
  rejected rather than overwritten.

### Fixed
- Saved recruits receive normal individual death and town recovery, using their
  own banks, including when a parked character rejoins in town.
- Party identification and perception consider every living active ally.
  Consumable stat gains no longer give saved recruits free mirrored increases.
- Replacing a chest-opening command cancels only the issuing character's
  opening; switching control preserves committed actions and the original opener.
- Switching characters saves both co-op players' live encounters, including
  encounters started after teleporting, so they survive reloading.
- Interrupted save preparation and blocked cleanup retain recovery journals.
  A failed journal deletion can no longer turn a committed save into a rollback
  or delete a newly saved character.
- Recovery-required parties cannot be retired, deleted, or mutated before
  recovery and reload.

## [0.1.69] — 2026-10-12

Mage allies, targeted item spells, and more reliable companion support.

### Added
- Mage is available as a primary or secondary Tavern ally guild, subject to
  the existing race, alignment, and guild eligibility requirements.
- A new ally **Charm** toggle controls automatic recruitment of suitable
  monsters during hostile combat and binding maintenance outside combat.
- Owned companions show qualitative binding/contentment assessments, clearer
  stability-face indicators, and a distinct permanent-binding icon.
- Optional **Use library knowledge to filter available spells** setting filters
  manual enemy spell choices using the acting player's monster knowledge.
  It is off by default and does not change automatic ally spell decisions.
- Friendly and peaceful monster-group buttons can select offensive spell and
  item targets without provoking the encounter.

### Changed
- Learned Control, Restrain, and Domination are cast on a selected companion
  through its context menu, rather than the generic Cast list or action bar.
- Spell-casting items used from inventory, equipped gear, or the hotbar offer
  useful recipient, destination, or locate/retrieve target pickers as needed.
  Binding items, including Life Domination, select a specific companion.
- Offensive spells and spell-casting items retain the selected monster group
  when a peaceful encounter becomes combat.
- Raise-item pickers distinguish dead characters, carried companion bodies,
  and dead roster companions.

### Fixed
- Manual spell availability and peaceful casting now respect the current
  encounter, recipient state, and original combat restrictions.
- Ally behavior and per-spell toggle changes made during combat apply to the
  live ally and remain in effect after combat ends.
- Shared co-op ally support preserves live HP, SP, and ailments instead of
  reverting to stale saved state.
- Item targeting preserves the actual item and companion across normal combat
  rounds; canceled or invalidated requests spend no charges. Newly created
  companion instances no longer report missing identity-metadata errors.
- Equipped-only spell items work from the hotbar, and successful item revival
  clears the ally's downed state.
- Item relocation settles the outgoing encounter and activates the destination
  room's encounter instead of carrying the old fight into the new room.
- NPC status icons keep font-relative sizing without the image-unit API
  dependency that could prevent the dungeon script from loading.

## [0.1.65] — 2026-10-11

More ally guild choices, exploration support, and clear cursed-item removal.

### Added
- Optional **Indestructible equipped items** setting protects equipped items
  from destruction.
- Optional **Don't restore drained stats in town** setting preserves temporary
  player stat drain instead of clearing it on returning to town.
- Seeker and Wizard are available as primary or secondary Tavern ally guilds.
  Seeker pairs with Warrior, Sorcerer, Healer, Paladin, Villain, Ninja, Thief,
  and Scavenger. Wizard pairs with Thief, Warrior, Ninja, Paladin, Scavenger,
  Healer, and Villain. All pairings work in both directions and still respect
  the original guild eligibility requirements.
- Villain allies can also pair with Sorcerer and Scavenger; Paladin allies can
  also pair with Scavenger.
- Context-sensitive ally commands for Depth Perception, Ethereal Portal,
  Find Direction, Displacement, and Teleport. Allies pay the spell cost while
  the effect applies to their owner; only currently usable commands appear.

### Changed
- Ally support AI can maintain levitation outside hostile combat with Feather
  Essence or Mass Levitate when buffs are enabled and spell/SP gates allow it.
- Newly offered Villain allies always have an allowed secondary guild, either
  leveled or pending.

### Fixed
- Auto-attached miscellaneous items such as Ball and Chain now appear as
  equipped items rather than unequipped inventory.
- Attached cursed items can be detached for the original removal fee through
  the General Store, Bank, or Character Panel, then sold or banked normally.
  Detachment works with a full backpack and does not duplicate the item.

## [0.1.60] — 2026-10-01

Clearer dungeon maps, reliable guild crest charges, and smoother spell travel.

### Added
- An offline biome-review atlas can be generated from the original dungeon
  maps for design review; it does not change the in-game dungeon or encounters.

### Changed
- The repository MIT License is now explicitly limited to the original
  distribution-site, documentation, and project-authored media files committed
  here. Downloadable game binaries and GitHub release assets are governed by
  the new End User License Agreement instead.
- `EULA.txt` is attached to every existing release and will be included in
  future Windows release archives.

### Fixed
- Ethereal Portal and other relocation spells now apply destination-room
  encounter effects immediately instead of waiting for the character to leave
  and re-enter the room.
- Monster names use more natural plural forms, including Hero and Goblin Shaman.
- Water and quicksand are both visible on dungeon-map cells where they overlap,
  with distinct wave patterns.
- Newly awarded guild crests start with their full charges. Depleted crests
  carried or equipped by the character recharge on returning to town.

## [0.1.55] — 2026-09-14

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
