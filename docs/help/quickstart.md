# Quickstart

This page gets you from a fresh install to your first few dungeon levels.

[Back to Help index](index.md)

## 1. Set up your game data

On first launch you'll see the **Set Up Your Game Data** screen. The remake ships
no original game content, so it needs to read data from your own copy of the
original game. You can point it at:

- a `.ZIP` archive (such as the bundled shareware, which contains dungeon levels
  1–3), or a loose `MORDOR.WIP` file,
- by picking a local file or folder,
- or by entering a download URL.

If you own the full retail game, point the importer at your own copy to unlock
all 15 dungeon levels. You can re-run this later, and optionally pull in the
original sound effects or monster art, from **Settings → Manage Original
Assets…**. I myself prefer the original sound effects to the bundled
AI-generated replacements, so importing the original SFX is recommended.

## 2. Create your hero

You play a **single** character (you'll gain companions later, but there's no
fixed four-slot party to manage). On the
[character-creation screen](character-creation.md) you'll:

1. Pick a **race** — this sets your stat ranges, allowed alignments, and how fast
   you earn experience.
2. **Allocate your stats** — STR, INT, WIS, CON, CHA, DEX. Each race starts at
   its minimum + 5 in every stat, then you spend that race's extra stat points
   with the +/− controls.
3. Choose an **alignment** (Good, Neutral, or Evil — some races restrict this).
4. Name your hero and confirm.

Everyone starts as a **Nomad, level 1**. You'll join better guilds soon.

### Which stats matter early?

- **CON** drives your hit points — see the leveling note below.
- **STR** and **DEX** boost both attack and defense once they pass their
  thresholds; high **INT** and **WIS** can also help A/D. **DEX** and **WIS**
  both help with chest disarming.
- **INT** and **WIS** give you spell points (SP = INT×5 + WIS×5) and many spells
  check stat requirements, so casters need them high. Keep at least **10 INT**
  and **10 WIS** at creation if you can: stat potions and tomes can permanently
  raise base stats, and tomes require 10 INT and 10 WIS to use.
- **CHA** matters if you plan to charm monsters into joining you as companions.

## 3. Get equipped and enter town

You begin with a small starter kit already equipped. Visit the
[General Store](general-store.md) to buy upgrades or replacements, adjust gear
from your [Character Sheet](character-sheet.md), then head into town and find
the staircase down.

Gold you bring to town is **automatically banked**. Gold found underground is
added to your carried haul until you return to town, where it is deposited for
you; chest traps do not steal gold.

## 4. Your first dungeon dive

- Move one step at a time through the maze. The map is always visible and fills
  in as you explore. (See [The Dungeon](dungeon.md).)
- You'll run into **monsters**. Fight, defend, cast spells, or try to flee.
- You'll find **chests**. Inspect for traps, try to disarm, then open them for
  loot. Risky, but that's where the good gear is.
- When your HP gets low or your spell points run dry, head back to the stairs and
  return to town to heal and bank your haul.

If you die, don't panic: you **respawn back in town**. There's no corpse to
recover and no morgue run — you just pick up where you left off (minus some
penalties). This makes early exploration much more forgiving than the original.

## 5. Leveling up — and the new "best route"

Return to your [Guild Hall](guild-hall.md) to spend experience and gain levels.
Each level makes you tougher and, in the right conditions, raises your maximum HP.

**Important change from the original:** in the 1995 game, your max HP was built up
by a *random roll every time you gained a level*, and those rolls depended on the
exact order in which you leveled your guilds — so veterans carefully sequenced
their guilds (and sometimes save-scummed the rolls) to squeeze out more HP.

In this remake, **max HP is a deterministic value computed from your CON and your
guild levels**. The order you level in no longer changes your HP, and there are no
HP rolls to re-run. The practical upshot:

- You can't "game" guild order for extra HP — pick guilds for their abilities, not
  to manipulate HP rolls.
- A high **CON** is the single biggest lever on your HP. Because max HP is
  recomputed from your *current* CON, raising your **base** CON (with tomes or
  stat potions) retroactively scales up your whole HP total — it doesn't matter
  whether you do it before or after grinding levels. Note that only permanent
  base-CON gains count; CON from equipped gear boosts your other stats but does
  **not** raise max HP.
- Plan your guild path around the powers you want (melee, casting, thieving),
  knowing your HP will land at the same place regardless of sequence.

See the [Guild Hall](guild-hall.md) page for the full details.

## Where to go next

- [The Dungeon](dungeon.md) — combat, chests, traps, and mapping in depth.
- [Guild Hall](guild-hall.md) — guilds, multi-classing, and quests.
- [Character Sheet](character-sheet.md) — equipment and spell casting.
- [Couch Co-op](coop.md) — play with a friend on one machine.
