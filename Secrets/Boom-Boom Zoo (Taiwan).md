# Boom-Boom Zoo

A four-player bomb game with 36 story stages and an animal password system.

## The passwords

Title entry 接關 opens a screen of four swings. Left and Right pick a swing,
Up and Down cycle its animal, A confirms. The game shows you your current
stage's code on the same swings after a game over, so these are not secret -
but here is the full list, left to right:

| Stage | Code | | Stage | Code |
|---|---|---|---|---|
| 1 | pig panda panda bear | | 19 | pig panda bear tiger |
| 2 | pig tiger panda pig | | 20 | tiger pig panda tiger |
| 3 | panda tiger pig panda | | 21 | bear bear bear panda |
| 4 | bear bear panda pig | | 22 | panda panda tiger tiger |
| 5 | panda panda panda tiger | | 23 | panda tiger tiger bear |
| 6 | tiger panda panda tiger | | 24 | bear panda panda pig |
| 7 | bear pig panda panda | | 25 | bear panda pig pig |
| 8 | tiger panda tiger bear | | 26 | bear tiger bear panda |
| 9 | panda pig panda pig | | 27 | pig bear panda panda |
| 10 | panda bear panda bear | | 28 | tiger tiger bear tiger |
| 11 | pig pig pig bear | | 29 | panda bear bear panda |
| 12 | tiger bear panda panda | | 30 | panda pig tiger panda |
| 13 | pig pig bear panda | | 31 | pig pig bear tiger |
| 14 | bear tiger tiger pig | | 32 | tiger tiger tiger panda |
| 15 | pig pig tiger bear | | 33 | bear tiger pig pig |
| 16 | tiger pig bear bear | | 34 | panda tiger panda pig |
| 17 | tiger bear pig pig | | 35 | panda panda panda pig |
| 18 | panda bear tiger panda | | 36 | bear panda bear bear |

Confirmed on the game.

## A stage skip that could not be triggered

The code contains a stage-skip: an in-game object that, sixty frames into its
life, watches for player one holding **exactly Select + L + R** and then ends
the stage as cleared. The skip mechanism itself works. But the object that
carries it could not be found in any stage that was tried - the title, the
password screen, character select, stage 1, and stages 6, 13, 21 and 36 - so
its trigger remains unknown.

## Four players

Players 2 to 4 join in through the multitap; the "Press Start" and 快加入
prompts on the HUD are the join path.

## MiSTer cheat pack

None yet. This game was surveyed for secrets but no cheat pack has been built.
