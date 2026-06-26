<p align="center">
  <img src="media/title_banner.png" alt="Dungeons of Dej'remake" width="560">
</p>

<h1 align="center">Dungeons of Dej'remake</h1>

<p align="center">
  A one-person, fully AI-assisted remake of the classic 1995 dungeon crawler
  <strong><em>Mordor: The Depths of Dejenol</em></strong>, rebuilt from scratch in the
  <a href="https://godotengine.org/">Godot Engine</a> for modern desktop and mobile.
</p>

This is an independent, non-commercial preservation/hobby project. It is **not
affiliated with, endorsed by, or sponsored by** MakeItSo Software or any current
rights holder of the original game. See [DISCLAIMER.md](DISCLAIMER.md).

> **What's published here:** compiled game builds, distributed as
> [Releases](../../releases). The remake's own source code is **not** published
> in this repository at this time.

## Project philosophy

This project is a deliberate experiment in solo, AI-driven game development:

- **One-person project.** Designed, built, and maintained by a single developer.
- **100% "vibe coded."** The entire codebase was written conversationally with an
  AI coding agent — describing intent and iterating, rather than hand-typing the
  implementation. Every gameplay rule is still held to the original game as the
  source of truth, with a strict test suite and a faithfulness rule behind it.
- **All assets are AI-generated.** Every piece of art (monsters, character
  portraits, items, spells, towns, UI) plus the music and sound effects shipped
  with the game are original, AI-generated replacements. **No original-game art,
  audio, or data is included** — you bring your own copy of the original game and
  the data is extracted locally on your device (see
  [Bring your own game data](#bring-your-own-game-data)).

## Screenshots

<p align="center">
  <img src="media/screenshots/town.png" width="80%"><br>
  <em>The town hub — guilds, shops, and services, with your hero's portrait and stats.</em>
</p>

<table>
  <tr>
    <td align="center" width="50%"><img src="media/screenshots/dungeon.png" width="100%"><br><em>Exploring the dungeon and facing an encounter.</em></td>
    <td align="center" width="50%"><img src="media/screenshots/character_spells.png" width="100%"><br><em>The character sheet — inventory, equipment, and spellbook.</em></td>
  </tr>
  <tr>
    <td align="center" width="50%"><img src="media/screenshots/tavern.png" width="100%"><br><em>Recruiting AI-driven allies at the tavern.</em></td>
    <td align="center" width="50%"><img src="media/screenshots/general_store.png" width="100%"><br><em>Buying and selling at the general store.</em></td>
  </tr>
</table>

## A look at the AI-generated art

### Monsters

<table>
  <tr>
    <td align="center"><img src="media/monsters/silver_dragon.png" width="150"><br>Silver Dragon</td>
    <td align="center"><img src="media/monsters/spectral_dragon.png" width="150"><br>Spectral Dragon</td>
    <td align="center"><img src="media/monsters/phoenix.png" width="150"><br>Phoenix</td>
  </tr>
  <tr>
    <td align="center"><img src="media/monsters/flame_devil.png" width="150"><br>Flame Devil</td>
    <td align="center"><img src="media/monsters/gorgon.png" width="150"><br>Gorgon</td>
    <td align="center"><img src="media/monsters/wolf_spider.png" width="150"><br>Wolf Spider</td>
  </tr>
</table>

### Character portraits

Portraits are generated per race, guild, gender, and progression tier, so your
character's look evolves as they grow in power.

<table>
  <tr>
    <td align="center"><img src="media/characters/female_elf_sorcerer_L60.png" width="150"><br>Elf Sorcerer</td>
    <td align="center"><img src="media/characters/male_giant_nomad_L120.png" width="150"><br>Giant Nomad</td>
    <td align="center"><img src="media/characters/male_human_thief_L120.png" width="150"><br>Human Thief</td>
  </tr>
  <tr>
    <td align="center"><img src="media/characters/female_gnome_healer_L1.png" width="150"><br>Gnome Healer</td>
    <td align="center"><img src="media/characters/male_osiri_seeker_L250.png" width="150"><br>Osiri Seeker</td>
    <td align="center"><img src="media/characters/female_troll_villain_L120.png" width="150"><br>Troll Villain</td>
  </tr>
</table>

### Items

<table>
  <tr>
    <td align="center"><img src="media/items/adamantite_sword.png" width="96"><br>Adamantite Sword</td>
    <td align="center"><img src="media/items/holy_sword.png" width="96"><br>Holy Sword</td>
    <td align="center"><img src="media/items/ring_of_flames.png" width="96"><br>Ring of Flames</td>
    <td align="center"><img src="media/items/crystal_of_healing.png" width="96"><br>Crystal of Healing</td>
    <td align="center"><img src="media/items/tome_of_learning.png" width="96"><br>Tome of Learning</td>
    <td align="center"><img src="media/items/potion_of_health.png" width="96"><br>Potion of Health</td>
  </tr>
</table>

### Spells

<table>
  <tr>
    <td align="center"><img src="media/spells/firebolt.png" width="96"><br>Firebolt</td>
    <td align="center"><img src="media/spells/sphere_of_flames.png" width="96"><br>Sphere of Flames</td>
    <td align="center"><img src="media/spells/ice_spray.png" width="96"><br>Ice Spray</td>
    <td align="center"><img src="media/spells/teleport.png" width="96"><br>Teleport</td>
    <td align="center"><img src="media/spells/minor_heal.png" width="96"><br>Minor Heal</td>
    <td align="center"><img src="media/spells/resurrect.png" width="96"><br>Resurrect</td>
  </tr>
</table>

## What this remake changes

The remake stays faithful to the original's formulas and content, but
modernizes the structure of play:

- **Single-player _or_ local couch co-op.** Play solo, or pair two independent
  characters in a local two-player session on one machine — each player drives
  their own input device (gamepad, keyboard + mouse, or touch).
- **AI-enabled allies.** Recruit NPC adventurers at the tavern and charm monsters
  to fight at your side; companions act and support **autonomously** through a
  combat AI. A solo hero can lead up to four companions.
- **One hero, not a four-slot party.** You control a single character (plus
  companions) instead of micromanaging a fixed party of four.
- **No aging.** The original's aging mechanic — and the death risk it carried —
  is removed entirely.
- **Gold is auto-banked.** Your gold is deposited safely on entering town, so you
  never carry it (or risk losing it) into the dungeon.
- **Death sends you back to town.** No corpse to recover and no morgue trip — you
  respawn in town and carry on.
- **Stat drain is recoverable.** Drained stats are restored when you return to
  town — for a fee — instead of the loss being permanent.
- **Guild quests are flexible.** Quests can be completed with any guild active.
- **Reimagined presentation.** A 2D top-down map with paperdoll monster art,
  rather than the original's 3D first-person corridors.
- **Full controller & touch support.** Gamepad focus navigation with a radial
  hotbar, plus a dedicated phone layout with an on-screen d-pad.

## Bring your own game data

The released builds ship **no original game content** — no maps, items,
monsters, spells, artwork, or audio from the original game. Instead, on first
launch the game asks you to point it at your **own copy** of the original Mordor
installer, and it extracts the data it needs locally on your device.

For convenience, the freely redistributable **shareware** distribution of the
original game is included in this repository at
[`tests/fixtures/MORDOR11.ZIP`](tests/fixtures/MORDOR11.ZIP). Redistribution of
that shareware package is **explicitly permitted by the original publisher** (see
[`tests/fixtures/README.md`](tests/fixtures/README.md)). It contains the first
3 dungeon levels. If you own the full retail game, you can point the importer at
your own copy to unlock all 15 levels.

The original game's data, artwork, and audio remain the property of their
respective rights holders and are **never** redistributed by this project in
extracted or transformed form.

## Getting started

1. Download the build for your platform from the [Releases](../../releases) page.
2. Launch it. On first run, the **Set Up Your Game Data** screen lets you import
   from a `.ZIP` (such as the bundled shareware) or a loose `MORDOR.WIP`, by
   picking a local file/folder or by entering a download URL.
3. (Optional) You may also extract the original sound effects and/or monster
   artwork from your own copy to use in place of the bundled replacements. This
   can be toggled any time later from **Settings → Manage Original Assets…**.

New to the game? Read the **[Player Help & Guide](docs/help/index.md)** — a
per-screen how-to plus a [Quickstart](docs/help/quickstart.md) and a list of
[differences from the original](docs/help/index.md). See the
[Changelog](docs/help/changelog.md) for what's changed between releases.

## Platforms

Windows, Android, and (work-in-progress) web/console targets.

## License

The original work in this repository — the remake itself and its compiled
builds — is released under the [MIT License](LICENSE), Copyright (c) 2026 Matteo
Prosperi.

**The MIT license applies only to this project's own original work.** It does
**not** apply to, and grants no rights in:

- the bundled shareware package (`tests/fixtures/MORDOR11.ZIP`) or any other
  original-game content, which remains the property of its rights holders and is
  redistributed only under the original publisher's own shareware terms; or
- the names, trademarks, and other intellectual property of the original game
  and its publisher.

See [DISCLAIMER.md](DISCLAIMER.md) for the full legal notice.
