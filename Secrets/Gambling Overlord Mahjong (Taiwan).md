# Gambling Overlord Mahjong

賭霸, © 1996 Funtech. Three gambling games in one cartridge, with historical
figures - Puyi, Xi Shi, Qin Shi Huang - as the opponents on the game-select
screen.

## Cheat codes and hidden input

There are none. Every button test is a single button, Select is never read,
and there is no reset combination.

## How the luck works

One random number generator serves the whole cartridge: a simple 16-bit
formula, `seed = seed * 2053 + 13849`. Two things about it are worth knowing.

**Every shuffle re-seeds from the frame counter.** Before each deal the game
copies its running frame count into the seed. So the entire outcome of a hand
is decided by one number - which frame the deal began on - and there are at
most 65,536 different deals per game.

**The power-on seed is uninitialised memory.** At reset the game adds up the
first four words of work RAM before clearing it. On hardware that starts with
zeroed RAM - a MiSTer, most emulators - that sum is always zero, and the boot
sequence is identical every time.

Whether your bet is placed before the cards are decided depends on the game:
in the 52-card game you bet first and the deck is shuffled after, but the
shuffle is fixed by the frame you pressed A on; in the 32-tile game the tiles
are already decided when you make your pick.

## The opponents' tiles are not hidden

There is no "show the opponent's hand" debug switch, because the game never
hides the hands in memory at all. All four mahjong hands are stored in plain
form and the game reads them every frame; "face down" is only a drawing
choice. Anyone who can read the console's memory can read every hand.

## Debug leftovers

**A slot-machine knob nothing turns.** One value is read seven times by the
slot machine - it sets which symbols the reels can land on and moves all
three win-line thresholds with it - and nothing in the game ever writes it.
It looks like a developer's "force the reels into range N" control.

**A one-way attract flag.** Sixty seconds of idling on the game-select screen
sets a flag that is never cleared: for the rest of the session the game
forces the A button every frame and treats Start as "stop the demo".

## Easter eggs

**A leftover PC sound file.** One voice clip is a Sound Blaster `.VOC` file
with its "Creative Voice File" header still attached - the only trace of a
development tool anywhere in the cartridge. It is in the Other Stuff folder.

Every word of Chinese in the game exists only as picture tiles; there is no
text, no build date, and no developer name.

## MiSTer cheat pack

| Cheat | What it does |
|---|---|
| Maximum bet | The bet multiplier is always 10 |
| Never go bust | The bust flag never sets, so no game over |
| Character slot 1 rich | The first character's balance reads 999,999 |
| Character slot 2 rich | Same for the second |
| Character slot 3 rich | Same for the third |
| Character slot 4 rich | Same for the fourth |
| Slot machine reel base 1 | Sets the dormant reel knob to 1 |

Balances are stored per character, not per seat, and which character you get
depends on the roster draw, so money is offered per slot. Everyone starts on
20,000. These were read from the code and not tested in play.
