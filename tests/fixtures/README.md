# Test fixtures

## `MORDOR11.ZIP`

The freely-redistributable **shareware ("PUBLIC") distribution** of *Mordor: The
Depths of Dejenol* v1.1 (1995), © MakeItSo Software. This is the unmodified
shareware package as originally distributed.

Redistribution is explicitly permitted by the bundled `MORDOR.WRI`:

> "Please feel free to distribute the PUBLIC (Shareware) version of MORDOR as you wish."

`FILE_ID.DIZ` labels it "Mordor 1.1 PUBLIC files".

### What it contains

A standard ZIP wrapping the original installer archives:
- `MORDOR.WIP` (standard ZIP) → `MDATA1/2/3/5/11.MDR`, `MORDOR.HLP`, `MG11.DLL`, all `*.MID`.
- `WAVES.WIP` (standard ZIP) → all SFX `*.WAV`.

The data tables (races, guilds, items, monsters, spells) are **identical** to the full
retail game. The **only** difference is the dungeon: the shareware `MDATA11` physically
contains **only the first 3 dungeon levels** (the full game has 15).

### Why it's here

Used as the source fixture for runtime data-extraction tests. The shipped game ships
**no** original-derived data/art/audio; each end user extracts from their own copy of the
original game. The original data/art/audio remain copyrighted by MakeItSo Software and
are **never** committed here in extracted/transformed form.
