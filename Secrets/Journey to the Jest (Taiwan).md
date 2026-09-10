# Journey to the Jest

Journey to the Jest - a platformer of the Journey to the West, with an
abtruse password system.

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

All eighteen were confirmed on the game. The game shows you a password
if you hit the guy at the end of the level with a ball.

## Cheat codes and hidden input

None.

## Debug leftovers

**A dead third menu entry.** The title menu's dispatch table has three
entries, but Select only ever toggles between the first two. The third does
nothing - a removed option.

**An orphaned five-digit number entry.** A complete little screen exists -
five digit slots, Left/Right to move, Up/Down to change, A to commit - with
its own font of hex digits, a star and a dash. Nothing calls it and nothing
reads its result. A debug entry screen left in the build.
