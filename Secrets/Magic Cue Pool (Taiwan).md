# Magic Cue Pool

魔法撞球, © 1996 Funtech. Pool with English-named opponents - Andraw, David -
over a world map with flags. Four modes: story, challenge, versus, practice.

## Cheat code

**Hold B + Select + Y + L + R together with a direction, during play, on your
own turn.** It presets both players' scores:

| Add | Your score | Opponent's score |
|---|---|---|
| Up | 61 | 20 |
| Down | 20 | 61 |
| Left | 60 | 60 |

It only works while it is your turn.

In the code it looks like a second version of the same six-button chord, on a
different screen, forces an immediate "scored, continue" turn result, but it's
uncertain where, if anywhere, it's triggered.

## Debug leftovers

**A hidden sprite bank.** One flag, compared against the value `$5A`, switches
the sprite table and sprite control register to an alternate set that retail
doesn't seem to use.

**A dead screen effect.** Some kind of per-scanline window effect exists in the code,
triggered by a flag that nothing sets.

## Easter eggs

**The developers signed it three times:**

- `1996 12 01 funthech all rights reserved gxl` - with Funtech misspelled
- `guo xiao lin 1996 12 01 copy right` - `gxl` spelled out
- `swtq.tsk ver105 95.12.26` - a module banner with its own version and a
  date a year older than the game, parked right after the reset entry where
  the CPU jumps over it

**23 KB of their assembler source.** A stretch of the ROM is plain-text
assembler source - thousands of `DB 000H,004H,...` lines - and the bytes it
assembles to are also in the ROM, elsewhere. An intermediate source file was
concatenated into the image alongside its own output. The full text is in the
Other Stuff folder.

**The 2 MB cartridge is a 1 MB game stored twice**, byte for byte.

