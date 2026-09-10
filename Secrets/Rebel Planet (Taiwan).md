# Rebel Planet

叛星 - a turn-based squad tactics game, not the shooter its cover suggests.
One controller only; player two is never read.

## Debug keys that shipped

Two developer keys are live in the retail game, inside the action menu that
opens for each of your units in battle. **They are read straight from the
code and have not yet been confirmed in play.**

**L wipes out every enemy on the map.** Every hostile unit is removed and its
health zeroed. Since the usual win condition is "no enemy left alive", this
clears the mission on the spot.

**R fully heals your whole squad.** Every friendly unit's health is reset to
its maximum, the same thing the game does for you after a victory.

## Cheat codes and hidden input

None beyond the two keys above. There is no button combination anywhere in
the game, and no Start+Select reset - both buttons are ordinary confirm keys.

## Easter eggs

**The programmer signed the save file.** The string `PROGRAMER JUH0WEN0HER`
sits in the ROM, and it is not decoration: the game compares it against the
first 22 bytes of the cartridge save, and if they do not match it starts a new
game. The programmer's name is the save file's signature. The zeros stand in
for spaces - the font has no space glyph - so the name reads roughly
"Ju H. Wen Her". It is one of only two pieces of English text in the entire
cartridge; the other is the standard Funtech/UMC notice.

**A skip.** Pressing A during the ending's scrolling sequence jumps to the
final screen.

**A set of sound commands nothing uses.** A routine for issuing an eight-slot
group of sound commands exists with nothing calling it - a whole bank of
sounds the game never plays.

There is no date, version, or other name anywhere in the ROM.

## MiSTer cheat pack

| Cheat | What it does |
|---|---|
| Unit slot 1 infinite HP | The unit in the first slot never loses health |
| Unit slot 2 infinite HP | Same for the second slot |
| Unit slot 3 infinite HP | Same for the third |
| Unit slot 4 infinite HP | Same for the fourth |
| Unit slot 1 infinite actions | The first slot's action budget never runs out |
| Unit slot 2 infinite actions | Same for the second |
| Freeze the turn counter | Turn-triggered reinforcements and events never fire |

Units are offered per slot because which slots hold your squad changes from
mission to mission. In the first mission your leader is slot 1. These were
read from the code and not individually tested in play.
