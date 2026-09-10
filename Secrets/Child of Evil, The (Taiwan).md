# The Child of Evil

The Son of Evil, Funtech's action RPG. It carries the console's most
elaborate developer secret: an island where the staff appear as characters.

## The developer island

Late in the game, reached by riding the Fire Dragon, there is a visit to
敦煌科技 "Dunhuang Technology" - Funtech's own offices - on Dunhuang Island.
The staff are the NPCs: An Shu, the artist on Journey to the Laugh; Long, a
programmer; Fang Wen, character design; the planner; A-Qing, stage art;
"Atom", the story programmer; the sound engineer; Si Xue, who programmed
Journey to the Laugh and reads your fortune; Xing, artist on a dinosaur game.
Other Funtech projects are name-dropped. What is there:

- **Long's level tool** - "Fancy a few levels? I can make your wish come true!"
- **A money wager** for a rich man's purse, one chance only, ending in "Money
  filled to the maximum"; the finance desk advances a thousand coppers.
- **A secret arts vendor** selling the Heaven Sever, Earth Rend and Frost
  Array formations for 5000, with anti-piracy lectures along the way.
- **A time-space vending machine**, and its key.
- **A players' club** that offers honorary membership: "Your name will go in
  the credits at the end of the game!" - and it does, through a name-entry
  screen in the ending.
- A long corporate speech about the A'Can and the domestic software trade.

## The debug mode

A block of four debug switches is dormant in the retail game - nothing sets
them, so they only work with the MiSTer cheat below. With debug mode on,
**the second controller becomes a debug pad:**

| Input | Effect |
|---|---|
| P2 Start | A hex overlay of the map number, position and pad bytes |
| P2 Select | Map number +1 |
| P2 B | Reload the map - warp to the number you picked |
| P2 Left | Toggle a movement-handling flag |
| P1 Select + Start (in the field) | Soft reset to the title |
| B in battle | Skip paths |

Also with the switch on, the opening village script offers a developer
shortcut straight to the credits, and holding A when the credits start puts
the roll under pad control.

**The credits name-entry hides a memory editor.** With debug on, pressing
Select in the name grid reads the ten characters you entered as hex: six
characters are an address, four optional characters a value. Address alone
shows the word there; address plus value writes it.

## Cheat codes and hidden input

Holding **A + B + X + Y + L + R** on pad 1 clears the debug switch - the only
thing in retail that touches it. One script check looks for exactly
**A + Up + Left + Y + L + R** on player one every 32nd poll during the opening
village; what it does was not established. Select+Start does nothing in retail
without the debug switch.

## Saves

Four slots in cartridge RAM, saved immediately from the field menu (X opens
it). There is a hidden good/evil meter, nudged by story choices, that changes
what some characters say.

## MiSTer cheat pack

| Cheat | What it does |
|---|---|
| Debug mode (player 2 pad) | Turns on the debug switch above |
| Debug flag - no music | The music switch from the same block |
| Character 1-8 - infinite HP and MP | 999 HP and MP for that party member |
| Infinite money | 銅錢 reads 9999 |
| All seven Mani jewels | The seven jewels fill the first inventory slots |

Character 1 is the hero, Shen Hao. The debug pad, the hero's stats, the money
and the jewels were all confirmed in play. A second pack exists for the
English translation build.
