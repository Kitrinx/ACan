# REBEL

叛星 - a turn-based squad tactics game.

## Cheat codes and hidden input

Two developer keys seem to be live in the retail game, inside the action menu that
opens for each of your units in battle.

**L wipes out every enemy on the map.** Every hostile unit is removed and its
health zeroed. Since the usual win condition is "no enemy left alive", this
clears the mission on the spot.

**R fully heals your whole squad.** Every friendly unit's health is reset to
its maximum, the same thing the game does for you after a victory.

## Easter eggs

**The programmer signed the save file.** The string `PROGRAMER JUH0WEN0HER`
sits in the ROM, and it is not decoration: the game compares it against the
first 22 bytes of the cartridge save, and if they do not match it starts a new
game. The programmer's name is the save file's signature. The zeros stand in
for spaces - the font has no space glyph - so the name reads roughly
"Ju H. Wen Her". It is one of only two pieces of English text in the entire
cartridge; the other is the standard Funtech/UMC notice.

**A set of leftover sound commands.** A routine for issuing an eight-slot
group of sound commands exists with nothing seeming to call it - a whole bank of
sounds the game never plays.
