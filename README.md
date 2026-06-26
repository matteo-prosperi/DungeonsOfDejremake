# Dungeons of Dejremake

A fan-made, from-scratch remake of the classic 1995 Windows dungeon crawler
**_Mordor: The Depths of Dejenol_** (originally by MakeItSo Software), rebuilt in
the [Godot Engine](https://godotengine.org/) for modern desktop and mobile
platforms.

This is an independent, non-commercial preservation/hobby project. It is **not
affiliated with, endorsed by, or sponsored by** MakeItSo Software or any current
rights holder of the original game. See [DISCLAIMER.md](DISCLAIMER.md).

> **What's published here:** compiled game builds, distributed as
> [Releases](../../releases). The remake's own source code is **not** published
> in this repository at this time.

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
