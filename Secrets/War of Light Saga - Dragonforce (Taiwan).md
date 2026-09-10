# War of Light Saga - Dragonforce

光明戰史 Dragon Force, © 1996 Kingformation. A strategy RPG, and almost none of
it is 68000 code - the game runs on its own Forth-style threaded language.

## Hidden input

**Hold L while entering the settings screen** (遊戲設定 on the title menu) and
the leafy green background becomes a starfield. Confirmed. It works from a
cold boot and needs nothing else.

**Start + Select together** resets the console back to the intro. Confirmed.

**Y is a second confirm button** everywhere B is.

## The music player

The third row of the settings screen, 音樂欣賞, is a sound test. B steps the
track and plays it. There are 26, and the game titles them:

    1  遠古的史詩       10 熱鬧的海港       19 大破壞
    2  戰鼓響起         11 神秘的氣息       20 神秘的敵人
    3  英雄的主題曲     12 金錢的樂章       21 海的變奏曲
    4  莊嚴的宮殿       13 教堂的聖歌       22 全力反攻
    5  吵雜的小鎮       14 戰士們的進行曲   23 最終之戰
    6  重工業之城       15 危機四伏         24 傳說的終章
    7  寂靜的村落       16 陷阱             25 勇士們的歡樂舞曲
    8  地底的死寂       17 妖魔大軍的威脅   26 安息的戰士們
    9  吉普賽舞曲       18 激烈的死鬥

## The debug mode

There is a developers' debug flag, and a chord that turns it on. **In the
battle command menu, hold A + X + L + R together, with B and Y released.** A
sound plays, a graphic loads, and the flag is set. It is one-way - there is no
chord to turn it off - and battle setup clears it again at the start of every
battle, so it lasts one battle at a time. Read from the code; not yet
confirmed in play.

With the flag on:

- Holding L while moving a unit on the battle map skips the range and path
  checks - free movement.
- Holding L on the map cursor shows the interpreter's data and return stack
  depths as `(A6):` and `(A7):`.
- Two extra numbers are drawn on the map screen.
- A script command unlocks sixteen story flags at once.
- The title screen gains A and Select handlers that step through indexed
  content, and the battle status screen gains a Select stepper.
- The game's built-in assertion framework wakes up: 46 of its own words are
  tagged with their names, and a stack error prints `ERROR!!!`, the word's
  name, and `DEPTH ERROR ??`. In normal play it never fires.

## Easter eggs

**The developers' own vocabulary.** Because the game is written in Forth, the
names the developers gave their words are in the cartridge:
`TOWN_MAP_MOVE`, `WAR_RPG_PROG`, `SELECT_SRAM_FILE`, `RPG_DIE_PROG`,
`MAGIC_FUNCTION_PROG`, `AI_CHR_FORTH_MOVE`, `CHUNCH_SHOP`, `DRAW_SEX_BORD`
(the gender-select border), and their own misspellings `LOCAET_WAR_CURCE` and
`STAUT`. The full list is in the Other Stuff folder.

The last megabyte of the 3 MB cartridge is compressed art; the final 108 KB is
blank. There is no date, version, or developer name anywhere in the ROM.

## MiSTer cheat pack

| Cheat | What it does |
|---|---|
| Debug mode | Holds the developers' debug flag on permanently |
| Infinite money | 現金 reads 99,999 |
| Level 51 and all four skills | EXP pinned at 5000; level and skills derive from it |
| Infinite HP | Current and maximum HP read 999 |
| Infinite MP | Current and maximum MP read 999 |
| Max attack | Base attack 900 |
| Max defence | Base defence 900 |
| Max agility | Agility 999 |

The stat and money cheats were confirmed on the status screen. The debug flag
does not disturb normal play. Whether the HP cheat survives combat was not
tested.
