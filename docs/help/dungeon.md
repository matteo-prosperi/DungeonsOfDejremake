# The Dungeon

The dungeon is the heart of the game: a maze of 30×30 floors full of monsters,
chests, traps, and treasure. This page covers moving around, fighting, looting,
and getting back out alive.

[Back to Help index](index.md)

## How to play

### Moving and mapping

- You explore one step at a time, turning and walking through the maze from a
  top-down view.
- Your **map is always visible while you play** and fills in as you explore. Map
  knowledge is shared across your characters — once a floor is mapped, you don't
  have to map it again.
- Watch for **stairs** and **chutes** to move between floors. The action to use a
  staircase or drop down a chute is labeled **Climb** (this is the action the
  original game called "Take").
- Some squares teleport you or spin you around and leave you **lost** — your
  position, floor, or facing may be unreliable until you step back into known
  territory or otherwise get your bearings.

### Combat

Fights happen in real-time rounds, driven by a combat timer that ticks about once
per second. Each round your hero acts once, your companions act on their own, and
the monsters act. Your hero's options:

- **Attack** — swing your equipped weapon(s) at a monster group. You get a base
  number of swings from your active guild plus extra swings from your weapons; if a
  target dies, remaining swings move on to the next monster. Some monsters may be
  resistant to attacks if your weapon is too low level.
- **Defend** — give up your swing for the round in exchange for much better
  defense.
- **Tank** — draw the monsters' attention to yourself while still attacking (at
  reduced damage). Useful for protecting weaker allies. Select it by pressing the
  **Defend** button twice: the first press queues Defend, and pressing again
  switches to Tank.
- **Cast a spell** — offensive spells chain through a monster group; healing and
  buffs support your side. (See the [Character Sheet](character-sheet.md) for
  casting.)
- **Use an item** — potions, scrolls, charged items, and more.
- **Move away** — walking away from an active fight interrupts the encounter.

Each round always resolves in a **fixed order**: your hero acts, then your
companions, then the monsters. There's no initiative roll — your side always acts
before the monsters. Your stance (attack/defend/tank) **sticks** from round to
round and even carries into your next fight, so you're not re-choosing it
constantly — change it whenever you like.

### Chests and traps

After a victory you may find a **chest** or **box** (chests hold the better loot).
Before grabbing the contents:

1. **Inspect** for a trap. Chests can be locked and trapped, and spotting the trap
   is based on WIS, with item WIS helping.
2. **Disarm** the trap if you can — success depends on your thieving ability plus
   WIS and DEX, and gets harder the deeper you are.
3. **Open** to claim the loot. If you misjudge it, the trap goes off — fire, shock,
   poison, disease, and worse.

### Staying alive

- Keep an eye on your HP and spell points. When either runs low, head back to the
  stairs and return to town to heal, bank your loot, and restock.
- The deeper you go, the better the rewards — and the deadlier the monsters and
  traps.

## Differences from the original

- **Top-down, not first-person.** The original was a 3D first-person corridor
  crawler. This remake presents the dungeon as a 2D top-down grid with fog-of-war
  and paperdoll monster art.
- **Death sends you back to town.** Instead of leaving a corpse to recover via a
  morgue, falling in the dungeon respawns you in town. An ordinary death is
  forgiving (you're always raised), though some penalties apply. Walking or
  teleporting **into solid rock** is the dangerous exception and can permanently
  cost you stats — so use the teleport tools carefully.
- **Banked gold is safe.** Gold found during a dive is carried until you return
  to town, where it is auto-deposited. Certain monsters can steal carried gold;
  you reclaim it if you win the fight, but lose it if the thief escapes. No trap
  steals gold.
- **Tank** is a new stance unique to this remake: unlike a passive guard, a tank
  keeps attacking (for reduced damage) while drawing the most aggro to protect the
  group.

[Back to Help index](index.md)

