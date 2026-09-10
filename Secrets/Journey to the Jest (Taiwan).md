# Journey to the Jest

Journey to the Laugh - a platformer of the Journey to the West, with a
password system the game never tells you about.

## The password system

At the title, **press Select** and the single menu line changes from 遊戲開始
to 密碼輸入 - password entry. Start opens a screen of ten icons in two rows:
Sun Wukong, Pigsy, Sha Wujing, Tang Sanzang and the white horse, then the
same five from behind. Left and Right move, Up and Down switch rows, A enters
a symbol, B clears. Numbering the icons 1 to 5 across the top and 6 to 10
across the bottom:

| Password | Where it takes you |
|---|---|
| 1 5 10 3 | Skull cave, green totem |
| 9 6 2 10 | Pink cavern with rope platforms |
| 4 2 4 1 | Skull cave with cobwebs |
| 5 3 8 4 | Cactus flats |
| 8 1 7 5 | Sand dunes |
| 1 1 4 3 | Cloud flight over mountains |
| 2 7 3 1 | Dark cave with a cart |
| 10 1 4 7 | Snowy pines |
| 4 5 10 3 | Cave archway |
| 3 4 1 5 | Night sky with pipes |
| 1 10 8 9 | Grey-roofed temple |
| 8 2 3 4 | Green mossy wall |
| 2 4 3 1 | Purple stone and water |
| 7 5 2 3 | Underwater |
| 6 2 7 6 | Temple gate with guardian statues |
| 5 1 6 2 | Skull cave, later visit |
| 1 3 9 6 | Stalactite cave with lava |
| 9 3 2 1 | Cloud flight, final |

All eighteen were confirmed on the game. The game never shows you a password -
they must have been printed in the manual.

## Cheat codes and hidden input

There is no button code. Any button skips a story panel, Start pauses (and
greys the whole screen), and Start ends the attract demo.

## Debug leftovers

**A dead third menu entry.** The title menu's dispatch table has three
entries, but Select only ever toggles between the first two. The third does
nothing - a removed option.

**An orphaned five-digit number entry.** A complete little screen exists -
five digit slots, Left/Right to move, Up/Down to change, A to commit - with
its own font of hex digits, a star and a dash. Nothing calls it and nothing
reads its result. A debug entry screen left in the build.

## Lives

Five lives and three continues. There is no saving - the cartridge never
touches its save RAM.

## MiSTer cheat pack

| Cheat | What it does |
|---|---|
| Infinite lives | The life count never drops |
| Infinite health | Both health meters stay full |
| Always hold the red peach | The item slot always holds a red peach |
| Always hold the pink peach | Same, pink |
| Always hold the gold peach | Same, gold |

The three peach cheats are alternatives. Infinite health does not stop falls -
pits kill regardless - so infinite lives is the one that covers pits. Lives and
health were confirmed in play.
