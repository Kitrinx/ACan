# Sango Fighter

A one-on-one fighting game based on the Romance of the Three Kingdoms - the
Super A'Can port of Panda Entertainment's PC game. Twelve generals.

## Cheat codes and hidden input

There are none. Every button test in the game is a single button. Select is
never read at all, so there is no Start+Select reset. There is no hidden
thirteenth character - the select cursor stops at twelve and so does every
character table.

## Options worth knowing

The options screen's time-limit toggle is a real infinite-time switch: with it
on, the round timer sits at 99 and never counts down.

## Debug leftovers

**A layer and scroll viewer nobody can reach.** A complete routine sits in the
code with no way in from the running game. Had it been wired up, L and R would
cycle each tilemap layer's mode, the d-pad would free-scroll the screen, Left
and Right would step through an asset index of 93 entries, and B would leave.
It is a developer's graphics viewer left in the build.

**Two dead win counters.** Two words are bumped every time a round is won and
then never read, shown, or reset. They are the ghosts of statistics the PC
version kept.

## Easter eggs

**The developers' own source code is in the cartridge.** Fragments of the
68000 assembly source - real lines of it, with the original symbol names like
`p2_airatk`, `p1_hitback`, `BACK_RATE`, labels like `check_hitted_act` and
`p2_air_defeat`, a commented-out `play_voc1k_p2_lose`, and an English comment
reading "check joybuf is 6 kinds" - are baked into the graphics data, where
stale editor buffers got assembled in with the artwork.

**75 PC sound files, headers and all.** The voice clips are Sound Blaster
`.VOC` files copied straight from the PC original with their "Creative Voice
File" container headers intact. A cartridge has no use for the headers; they
are just along for the ride.

**Half a megabyte of mirror.** The last 512 KB of the 3 MB cartridge is a
byte-for-byte copy of the 512 KB before it.

There is no date, version, or developer name anywhere in the ROM - the source
fragments are the only trace of who wrote it.

## MiSTer cheat pack

| Cheat | What it does |
|---|---|
| Player 1 infinite health | Health bar stays full |
| Player 2 infinite health | The opponent's bar stays full (for two-player practice) |
| Player 2 dies in one hit | Any hit knocks the opponent out |
| Infinite round time | Timer pinned at 99 |
| Player 1 full power meter | Special-move gauge stays full |
| Player 1 wins the match | Counts as two rounds already won |

The two player-2 health cheats are alternatives - enable one or the other.
Infinite round time was confirmed in play; the rest are read from the code.
