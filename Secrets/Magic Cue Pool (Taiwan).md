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

Six buttons at once, so nothing in ordinary play trips it. It only works while
it is your turn - on the opponent's turn the game is on a different code path
and ignores it. Confirmed on the game. The winning score is 240.

A second version of the same six-button chord, on a different screen, forces
an immediate "scored, continue" turn result. Not confirmed.

## Cheat codes that are not there

No Start+Select reset. No password or continue system of any kind - every way
into a game zeroes both scores, and the cartridge never touches its save RAM.
Nothing persists.

## Debug leftovers

**A hidden sprite bank.** One flag, compared against the value `$5A`, switches
the sprite table and sprite control register to an alternate set that retail
can never select - nothing in the game ever stores that value. What the
alternate bank looks like is unknown.

**A dead screen effect.** A per-scanline window effect exists in the code,
gated on a flag that nothing sets.

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

## MiSTer cheat pack

| Cheat | What it does |
|---|---|
| Infinite shot time | The shot clock stays at 11 seconds |
| Player 1 wins now | Your score reads 240, the winning total |
| Player 2 held at zero | The opponent's score never rises |
| Turn never ends | The game always thinks you potted something |
| Hidden sprite bank | Turns on the alternate sprite bank |

The two score cheats are the same addresses the cheat code writes, so they are
confirmed. The rest were read from the code and not individually tested.
