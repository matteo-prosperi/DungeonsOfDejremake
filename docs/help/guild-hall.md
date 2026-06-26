# Guild Hall

The Guild Hall is where you join guilds, spend experience to gain levels, earn new
abilities, and take on quests. Your guild memberships define what your hero can
do.

[Back to Help index](index.md)

## How to play

### Joining guilds

You start as a **Nomad**. At the Guild Hall you can join other guilds when you meet
their stat and alignment requirements. You can belong to **many guilds at once** —
your hero is a blend of every guild they've joined.

- Your **second** guild is free. Each additional guild costs gold.
- Guild-derived ratings don't add together — for overlapping combat and skill
  scores you use the best guild's score, while spells can be learned from any
  guild that teaches them.
- Only your single best guild contributes to your attack/defense at a time.
- Some guilds are alignment-locked (for example, Paladins must be Good, Villains
  Evil, Thieves and Healers Neutral).

A quick sense of the roster: **Warrior** is the best pure fighter and HP guild;
**Ninja** adds extra attacks; **Thief**/**Scavenger** excel at traps and locks;
**Mage**, **Sorcerer**, and **Wizard** are the casters; **Healer** is the only
truly effective healing guild; **Seeker** focuses on exploration and navigation;
the **Nomad** levels fastest and is a great early base.

### Leveling up

Spend the experience you've earned in the dungeon to gain levels in your active
guild. Levels can improve your attack/defense and abilities, unlock new spells
for casting guilds, and raise your maximum HP when they improve the HP total for
your current guild-level spread.

How much experience a level costs depends on your **race** (your XP modifier) and
your **guild** (its XP multiplier). Fast-XP guilds like the Nomad are cheap to
level; powerful guilds like the Wizard cost much more per level.

### Quests

Some guilds will occasionally require a **quest** — kill a specific monster or
fetch a specific item — before they'll let you take your next level. Complete the
objective in the dungeon and return to claim your level.

If you can't (or won't) finish a quest, you can **forfeit** it — but this demotes
you in that guild by several levels (more at higher levels), and your HP, A/D, and
level-gated abilities are recomputed downward to match the lower level. Forfeiting
is a real setback, so treat quests as worth completing.

### How HP works (and why your leveling route changed)

Your **maximum HP** in this remake is a single deterministic value worked out from
your **CON** and your **guild levels**. The rules of thumb:

- For each guild-level tier you've reached, the game looks at every guild that
  has reached that tier and uses the best expected HP gain for that tier. Tiers
  above a guild's HP cap use that guild's minimum HP gain.
- A high **CON** adds bonus HP per qualifying level (the bonus grows the further
  CON is above 16), so CON is by far the biggest lever on your total HP. Only your
  permanent **base** CON counts here — raise it with tomes or stat potions; CON
  from equipped gear does **not** increase max HP.

Because the total is computed from your current `(CON, guild levels)` state, **the
order in which you leveled doesn't matter, and there are no HP rolls.** This
changes the optimal strategy compared to the original (see below): keep your base
CON high — raising it later scales your whole HP total just as well as raising it
early — and pick guilds for their powers, not to manipulate HP.

## Differences from the original

- **HP is deterministic — the optimal leveling route changed.** In the 1995 game,
  HP was built up by a *random roll on every level-up*, and the result depended on
  the exact order you leveled your guilds. Players exploited this by sequencing
  guilds carefully (and re-rolling) to maximize HP. Here, your max HP is computed
  directly from your CON and guild levels, so:
  - level order no longer affects your HP total,
  - there are no HP rolls to re-roll or save-scum,
  - the winning play is to **keep your base CON high** (via tomes and stat
    potions — equipped CON gear doesn't count toward HP) and choose guilds for
    their abilities. Raising CON at any point retroactively scales your whole HP
    total, since every HP change — creation, each level-up, and quest forfeit —
    recomputes to the same correct value for your current CON and guild levels.
- **Quests are guild-flexible.** You can complete a guild's quest while any guild
  is active.
- **Retire Character.** The Guild Hall offers a convenience option to retire a
  character.

[Back to Help index](index.md)
