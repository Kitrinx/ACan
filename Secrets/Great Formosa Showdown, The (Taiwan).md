# The Great Formosa Showdown

福爾摩沙大對決 - a two-player competitive falling-block puzzle game in the Puyo
Puyo family, by AV artisan.

## Cheat codes and hidden input

There are none. Every button test in the game is "any of these buttons", never
a combination. Select is never read, so there is no soft reset. Start is the
only button the title screen answers.

## Debug leftovers

**An auto-play switch that nothing turns on.** One flag, when set, makes the
game stop reading a player's controller and feed it a made-up "every action
button pressed" input each frame. Nothing in the game ever sets it. It is the
remains of a demo auto-player or a computer opponent that was taken out.

**Four cut piece types.** Ten piece definitions exist; the game's dispatch
table reaches only six. The other four - and the three graphics tables only
they refer to - are pieces that were designed and then dropped.

**Two game states nobody enters.** The main state machine checks for states
`$13` and `$0D` and has code for them, but nothing ever switches to either.

## Easter eggs

**The codename.** At the very start of the ROM, right after the CPU's vector
table, sixteen bytes read `Lancelot 002 95'` - project codename Lancelot,
build 002, 1995. It is the only developer text in the cartridge.

**The characters have English names.** The character select labels its
portraits *Arbei* and *James* - Latin nicknames on a cartridge whose every
other word is Chinese.

**The AV artisan logo card** plays before the title on every boot.

## MiSTer cheat pack

| Cheat | What it does |
|---|---|
| Player 1 plays itself | Turns on the dormant auto-play switch for player one |
| Player 1 never tops out | Player one's stack can never reach the kill line |
| Player 2 never tops out | Same for player two |
| Slowest drop speed | Pieces fall at the game's slowest rate for good |
| One round wins the match | The first round win takes the match |
| Player 1 score 999999 | Player one's score reads 999,999 |

These were read from the code and not individually tested in play.
