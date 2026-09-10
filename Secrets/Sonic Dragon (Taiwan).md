# Sonic Dragon

Also known as Speedy Dragon. A platformer by AV Artisan, with two stage-select
codes and a hidden crash handler.

## Stage select codes

Both are entered on the title screen, one button at a time, and you have
about four seconds before the attract demo starts. Then press Start.

**Code A: Up, Up, Down, Down, Left, Left, Right, Right.** Start then opens a
six-entry numbered stage list.

**Code B: Left, L, Right, R, then press Down while holding A, B, X and Y
together.** Start then opens a three-entry list of named stages: 綠野山坡
(green hills), 機械戰地 (machine battlefield), 夜空突襲 (night-sky assault).

Both confirmed on the game.

**Start modifiers.** With code A entered, holding a button as you press Start
adds an effect: **X** lets you jump again in mid-air; **L** turns the sound
driver off. The mid-air jump was confirmed.

## The crash screen and its memory browser

Every CPU exception in the game leads to a crash screen that dumps the
registers with labels like `BUS ERROR`, `ADDR ERROR`, `ILL CODE`, `DIV BY 0`.
On that screen, the border blinks, and the game is waiting for a code:

**L, R, L, R, Up, Up, Down, Down, Left, Right, Left, Right, Select.**

Enter it and the crash screen becomes a memory browser: Start resets the
address to zero; A, B, X and Y pick a step of 1 MB, 64 KB, 4 KB or 256 bytes;
Up and Down move by that step; L and R switch the display mode. Read from the
code - you would need to crash the game to see it.

## Debug leftovers

**The input recorder.** The attract demos are recordings of real play, and the
tool that made them - a routine that appends the pad word to a buffer each
frame - is still in the ROM, with nothing calling it.

## Other

Start pauses. The cartridge never touches its save RAM. The title is credited
to AV Artisan on screen even though the ROM carries the standard Funtech/UMC
notice.

## MiSTer cheat pack

| Cheat | What it does |
|---|---|
| Infinite lives | The life count stays at 3 |
| Jump in mid-air | The mid-air jump modifier, always on |
| Stage select - 6 stages | Start on the title opens the six-entry list |
| Stage select - 3 stages | Start on the title opens the three-entry list |

The two stage selects are alternatives; if both are on, the three-stage list
wins. All four were confirmed in play.
