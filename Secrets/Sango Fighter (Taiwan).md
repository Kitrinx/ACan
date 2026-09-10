# Sango Fighter

A one-on-one fighting game based on the Romance of the Three Kingdoms - the
Super A'Can port of Panda Entertainment's PC game. Twelve generals.

## Cheat codes and hidden input

None.

## Debug leftovers

**A layer and scroll viewer nobody can reach.** A complete routine sits in the
code with no obvioua implemented trigger. Had it been wired up, L and R would
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
File" container headers intact. The game ignores the headers entirely and
streams the raw bytes into the sound chip - which is just as well, because two
bytes in every header are wrong and would confuse a real VOC player.

**Half a megabyte of mirror.** The last 512 KB of the 3 MB cartridge is a
byte-for-byte copy of the 512 KB before it.
