# Chinese Professional Baseball League

超級中華職棒聯盟, © 1995 C&E. The six CPBL clubs, six stadiums, and - unusually
for this console - four-player support.

## Hidden power-on diagnostics

The factory test screen is still in the retail cartridge, and it still works.

**Hold A + B + X while the console powers on.** The game runs a memory test on
the cartridge's battery-backed save RAM and shows `RAM OK` on a black screen,
then halts. **This one is destructive** - it overwrites the save area to test
it, so it will wipe your season.

**Hold B + X + Y while the console powers on.** The game checks the save RAM's
stored checksum and shows either `BATTERY OK` or `BATTERY ERROR`, then halts.
This one is safe; it only reads.

Either way you have to power off to get back. Both were confirmed on the game.

## Four players

The matchup screen offers `1P vs CPU`, `1P vs 2P`, `1P·2P vs CPU`, `1P vs 3P`,
`1P·2P vs 3P·4P`, `1P·CPU vs 2P·CPU`, `1P vs 2P·CPU` and `CPU1 vs CPU2`. With a
multitap, two people can share each side.

## Debug leftovers

**A hardware debug port.** The code contains routines for sending bytes and
strings out of a development-board port that the real console does not have.
One byte is still sent from live code every game.

**Two dead parameter editors.** Two pad-driven debug screens survive in the
ROM with no way to open them: one edits three numbers with the d-pad
(hundreds with X held, tens with A held) and dumps them to the debug port on
Start; the other is driven from the second pad and injects values straight
into a live game object. Their front ends were cut; the back ends were not.

## Passwords and saves

There is no password system. The game saves seasons to the cartridge's
battery RAM. The name-entry alphabet is missing the letters U and V.

## Easter eggs

The result screen has a vocabulary all its own: a perfect game is 完全比賽勝,
a walk-off home run is 再見全壘打勝, and losing badly is 技不如人敗 - "lost to
the better side". There is no build date, version, or developer name anywhere
in the cartridge, and no padding either - it is full to the last byte, ending
in the middle of a font.
