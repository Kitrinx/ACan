# THE SON OF EVIL (魔界之子) — Items, Equipment, Arts & Bestiary Guide

Platform: Super A'Can (Funtech, 1995)
Guide version 1.0 — 2026-09-10
Names follow the English translation patch. Where the patch's in-game short
name differs from how a character says it in dialogue, the dialogue form is in
parentheses on first mention.


---------------------------------------------------------------------------

## TABLE OF CONTENTS

    [1]  How the game works: pools, stats, damage
    [2]  The eight characters
    [3]  Usable items — healing, cures, misc
    [4]  Battle attack items
    [5]  Key and story items
    [6]  Weapons by type
    [7]  Armor by type
    [8]  Arts — Skills (KP)
    [9]  Arts — Magic (MP)
    [10] Arts — Inner and Light manuals
    [11] Bestiary
    [12] Encounter tables
    [13] Shops and inns
    [14] Level, EXP and growth tables
    [15] Secrets, dummy content and bugs
    [16] Unverified points and sources

Search for the bracketed tag to jump to a section.

---------------------------------------------------------------------------

## [1] HOW THE GAME WORKS

### Three pools

Every character has three pools:

| Pool | Used by | Restored by |
|---|---|---|
| **HP** | Damage. 0 = down. | Herb line, Elixir, Mica Cap, Spirit, MercyHymn, Med Chant, Transmute, inns |
| **KP** | *Skills* (weapon arts, the "武功" side of the Arts menu) | Chi Dust, Restore, Strength, Sweetbud, Elixir, Mica Cap, MercyHymn, inns |
| **MP** | *Magic* (spells, the "法術" side) | Samadhi, Dragoncap, Mica Cap, inns |

Fang, Furong and Nameless have **0 MP at every level** and cannot learn or use
any Magic. Everyone can use Skills.

### Stats

| Stat | Where it comes from |
|---|---|
| **Atk** | base Atk + weapon Atk + favoured-weapon bonus (+2 for a character's first favoured type, +1 for the second) |
| **Def** | base Def + the Def of all six equipment slots |
| **Agi** | base Agi + the Agi of all six slots (weapons and heavy armor are negative) |

Base Atk and base Def rise by **+1 per level** (if several levels arrive at once
from one fight, the gain is 2n−1 for n levels). Base Agi **never grows** — only
equipment and the two Light manuals change it. Reading an Inner or Light manual
adds permanently to the base stats (see [10]).

Max HP, KP and MP are fixed per character per level (see [14]). Leveling up
refills all three.

### Turn order

Each combatant has a turn gauge that fills by its speed every tick; speed is
Agi clamped to 8..63. A full gauge = a turn. Slumber resets an enemy's gauge to
0; Whirlwind adds 50 % to an ally's speed for the fight.

### Damage — there is no randomness

Physical attacks, Skills, Magic and thrown items all use one formula:

    P = attacker power        (base Atk for arts and items — the weapon is NOT counted;
                               full Atk for a plain attack)
    D = defender Def
    poison on the attacker: P − 5.  Poison on the defender: D − 5.
    element match (see below) nudges P and D by 1..4.
    x = P − D  (floored at 0)
    damage = T[x] for x ≤ 30, where T =
        1,2,3,4,5,7,8,10,12,14,16,18,20,23,26,30,36,42,50,60,70,85,100,115,130,145,160,180,200,220,240
    damage = 30·x − 660 for x > 30
    plus (P − 5 − D/8) if that is positive.

So the same attack on the same enemy always does the same damage. The only
random element in combat is enemy behaviour and encounter choice.

**Range.** Enemies standing on the far side of the field (x > 204) take 1/8
less from a plain attack with a sword, blade or axe. Staves, spears and bows
are "reach" weapons and keep full power. The same rule scales enemy attacks.

### Elements *(bit names inferred from which arts carry them)*

Each attack carries an element word, each enemy a weakness/resistance word.
Where they overlap, P and D shift:

| Enemy weak to | P / D change | Enemy resists | P / D change |
|---|---|---|---|
| Fire | +1 / −1 | Fire | −1 / +3 |
| Water | 0 / −2 | Water | −1 / +2 |
| Lightning | +2 / 0 | Ghost | −1 / +3 |
| Venom | +2 / 0 | Holy | −1 / +4 |
| Ghost | +1 / −1 | | |
| Dark | 0 / −2 | | |
| Holy | +1 / −1 | | |
| Snake | +1 / −3 | | |
| Stone | +1 / −1 | | |
| Sword/Blade | +2 / 0 | | |
| Axe/Bow | +1 / −1 | | |
| Staff/Spear | +1 / −1 | | |

A plain weapon attack carries its weapon family bit and, for named blades, one
element (see [6]). Because the shift is a few points on the P−D difference, it
matters most early, when P−D is small and every point is a table step.

### Poison and venom

Two status bits: **poison** and **venom** (巨毒, "heavy poison").
- Walking: venom hurts every step, poison every other step. Damage per hit is
  maxHP/32 + 2. HP stops at 1 — it never kills.
- In battle: a poisoned attacker loses 5 power, a poisoned defender loses 5 Def.
  There is no per-turn damage in battle.
- Cured by Goldroot (poison only), Ice Pill (both), Med Chant, WhiteBird, and
  by resting at an inn. Battle end does **not** clear it.
- Sources: some enemy arts (Dragonswd and Centipede as used by enemies), story
  events, and the poison mist on the Pool map unless a Ward Pill has been used.

### EXP and money

Every living party member receives the **full** EXP of the fight (it is not
split). Money is shared. Both cap at 65,535.

### Shops

Buy price is fixed per item; selling returns exactly half. Items with price 0
("Unsold") cannot be sold or thrown away. Every skill manual sells for 250
(price 500) if you ever want to dump one.

---------------------------------------------------------------------------

## [2] THE EIGHT CHARACTERS

The party holds up to four of these eight. Favoured weapons give +2 / +1 Atk.

| # | Name | Favoured weapons | Magic? | L1 HP/KP/MP | L60 HP/KP/MP | Base Atk/Def/Agi at start | Starting gear |
|---|---|---|---|---|---|---|---|
| 1 | Hao (Shen Hao) | Sword, Blade | yes | 30/16/2 | 999/350/300 | 12/6/18 | Dirk, Straw Hat, Training, Sandals |
| 2 | Fang (Fang Tiangong) | Bow, Axe | **no** | 25/20/0 | 799/320/0 | 9/7/15 | Bamboo bow, Straw Hat, Training, Sandals |
| 3 | Furong | Staff, Spear | **no** | 20/14/0 | 899/300/0 | 8/6/16 | Cudgel, Cloth Cap, Training, Gloves, ClothShoe |
| 4 | Caiyi | Sword, Blade | yes | 15/10/12 | 699/270/350 | 6/4/15 | Iron Swd, Targe, Hide Cap, Training, ClothShoe |
| 5 | Hong (Hong Yuantong) | Blade, Axe | yes | 35/18/0 | 999/350/320 | 13/8/17 | Brass Sbr, Targe, Hide Cap, Rattan, HideCuffs, Hide Boot |
| 6 | Qiu (Daoist Qiu) | Sword, Spear | yes | 20/12/15 | 699/300/350 | 7/5/15 | Brass Swd, Fine Cap, Hemp Robe, Gloves, ClothShoe |
| 7 | Humuzhu | Blade, Bow | yes | 18/12/6 | 799/290/240 | 6/5/15 | Iron Sbr, Targe, Hide Cap, Hide Mail, HideCuffs, Hide Boot |
| 8 | Nameless | Axe, Staff | **no** | 35/16/0 | 999/350/0 | 11/7/17 | Iron Axe, Iron Shld, Iron Helm, Iron Mail, ClothShoe |

Starting gear is what the save-file seed holds; the story may change it before
you see the character. Levels on joining are set by the story.

Caiyi, Qiu and Humuzhu have the largest MP pools and are the casters; Hong and
Nameless have the most HP.

---------------------------------------------------------------------------

## [3] USABLE ITEMS

All usable in the field and in battle on one ally. A heal that changes nothing
(pool already full) is not consumed. Prices: buy / sell.

| Id | Name | Effect | Price |
|---|---|---|---|
| $01 | Herb | HP +50 | 20 / 10 |
| $02 | Angelica | HP +150 | 80 / 40 |
| $03 | Ginseng | HP +300 | 150 / 75 |
| $04 | Gourdcap | HP +600 | 300 / 150 |
| $05 | Chi Dust | KP +30 | 15 / 7 |
| $06 | Restore | KP +80 | 70 / 35 |
| $07 | Strength | KP +120 | 130 / 65 |
| $08 | Sweetbud | KP +200 | 180 / 90 |
| $09 | Elixir | HP +100 and KP +100 | 180 / 90 |
| $0A | Samadhi | MP +50 | 50 / 25 |
| $0B | Mica Cap | HP, KP and MP to full | 600 / 300 |
| $0C | Dragoncap | MP +150 | 300 / 150 |
| $0D | Reviver | **Does nothing.** Greyed out in the menu; its effect routine is empty. See [15]. | 900 / 450 |
| $0E | Clover | Picks one pool at random (HP 41 %, KP 30 %, MP 30 %) and fills it halfway from its current value to its max. Fails if that pool is already full. | 50 / 25 |
| $0F | Goldroot | Cures poison (not venom) | 25 / 12 |
| $10 | Ice Pill | Cures poison and venom | 120 / 60 |

There is no revive item and no "down" state to revive from: a character at 0 HP
can be given any HP item and will stand up. Herb is the cheapest way to do it.

---------------------------------------------------------------------------

## [4] BATTLE ATTACK ITEMS

Thrown at enemies; battle only; **consumed before the effect resolves**. Power
is the thrower's *base* Atk (level-only, no weapon) plus the item bonus, through
the normal damage formula. No item inflicts a status. Four of the thirteen are
duds: the code path for them is an empty return.

| Id | Name | Bonus | Targets | Element | Price |
|---|---|---|---|---|---|
| $11 | Diamond | +2 | all enemies | Lightning | 20 / 10 |
| $12 | Cinnabar | +6 | all enemies | Fire | 40 / 20 |
| $13 | Bonecap | +8 | all enemies | Venom | 60 / 30 |
| $14 | Peacock | **none — consumed, no effect** | — | — | 50 / 25 |
| $15 | Datura | +3 | all enemies | Venom | 25 / 12 |
| $16 | Realgar | +7 | all enemies | Snake | 50 / 25 |
| $17 | Bolt Ward | +16 | one enemy | Lightning | 45 / 22 |
| $18 | Fire Ward | **none — consumed, no effect** | — | — | 99 / 49 |
| $19 | GhostWard | +14 | one enemy | Ghost | 40 / 20 |
| $1A | Red Ward | **none — consumed, no effect** | — | — | 99 / 49 |
| $1B | Bind Ward | **none — consumed, no effect** | — | — | 99 / 49 |
| $1C | Rock Ward | +12 | one enemy | Stone | 35 / 17 |
| $1D | Sage Ward | plays the Sage Art animation; **no damage call** | — | — | 100 / 50 |

The all-enemy powders (Diamond, Cinnabar, Bonecap, Datura, Realgar) are the
bargains: 20–60 coins for a hit on every enemy, and since the bonus stacks on
base Atk they scale with level. Bolt Ward is the strongest single throw.

---------------------------------------------------------------------------

## [5] KEY AND STORY ITEMS

All price 0, cannot be sold or dropped. "Use" text is the in-game description;
which door each key opens is taken from that text, not traced through the event
scripts (the scripts hand items out and test for them by id, but were not
followed door by door).

| Id | Name | Description / use |
|---|---|---|
| $1E–$24 | Purple, Orange, Green, Blue, Yellow, White, Red Pearl | "One of the seven Mani Pearls." The seven-pearl quest; you start with the Orange one. |
| $25 | Old Jade | story item, no text |
| $26 | Earhorn | story item, no text |
| $27 | War Tally | story item, no text |
| $28 | Gold Bar | story item, no text |
| $29 | Key | story item, no text |
| $2A | Fragment | "Holy City passage." Using it shows the hint "the blade in water, the (…) in fire" — it points to the Moonblade. Not consumed. |
| $2B | Key A | Frees Zhang Kan |
| $2C | Key Q | The abbot's chest |
| $2D | Key C | Opens House 2 |
| $2E | Key D | Secret path |
| $2F | Key E | Tunnel door F |
| $30 | Key P | Castle, right wing |
| $31 | Key G | Castle basement 1 |
| $32 | Key H | Tunnel chest |
| $33 | Key I | Souvenir key |
| $34 | Key J | Castle basement 1 |
| $35 | Crystal | Turns the six mirrors |
| $36 | Ward Pill | Usable only on the Pool map: stops the poison mist there. Uses the whole stack. |
| $37 | Earplugs | Usable only on the Pool map: stops the periodic sound event there. Uses the whole stack. |
| $38 | Small Box | "A box of ill luck; Wuwang the old man wants it." |
| $39 | Key K | For the hole on floor 4 |
| $3A | Note | Readable: "First get the key to the third floor…" Not consumed. |
| $3B | Key O | Castle floor 2 |
| $3C | Painting | "Art." **Use it**: it is consumed and the SlowShade manual ($D8) falls out of the back. |
| $3D | Gold Bar | "Deco." |
| $40 | Key M | Iron City, main keep 1F door D |
| $41 | Key N | Iron City, east keep 2F chest |
| $42 | Key L | Iron City, main keep 1F door B |
| $43 | Key F | Iron City, main keep 1F door F |
| $44 | Key B | Vendor key (the "time-space vending machine") |
| $45 | Dunhuang | "Special." Story item. |
| $46 | Rope | "A stout rope." |
| $47 | Compass | Passive: while it is in the bag, maps flagged for it show an overlay (*inferred*: a minimap). "Use" does nothing. |

---------------------------------------------------------------------------

## [6] WEAPONS BY TYPE

Anyone can equip any weapon; the favoured types in [2] just add +2 / +1 Atk.
Skills that need a weapon type only appear in the battle menu while that type
is equipped. **Two-handed** weapons empty and lock the shield slot. Element is
the bonus a plain attack carries on top of its family bit (see [1]).

One weapon in every type is a placeholder: all zeros, priced 9999, never sold in
any shop and never referenced by the code. They are listed for completeness.

### Swords (劍) — one-handed unless marked; family bonus Sword/Blade

| Id | Name | Atk | Agi | Price | Hands | Element | Notes |
|---|---|---|---|---|---|---|---|
| $60 | Old Sword | 10 | +0 | 0 | one | - | story weapon |
| $61 | Heaven | 27 | +5 | 0 | one | Lightning | story weapon |
| $62 | Dirk | 2 | +0 | 30 | one | - |  |
| $63 | Iron Swd | 6 | -1 | 120 | one | - |  |
| $64 | Brass Swd | 10 | -1 | 300 | one | - |  |
| $65 | Goldfish | 11 | -1 | 650 | one | - |  |
| $66 | Desire | 15 | -2 | 800 | one | Fire |  |
| $67 | Claymore | 11 | -1 | 450 | two | Dark |  |
| $68 | Twin Swd | 16 | -1 | 900 | two | Lightning |  |
| $69 | Peachwood | 7 | +0 | 200 | one | Holy |  |
| $6A | Tianpeng | 12 | +2 | 750 | one | Ghost |  |
| $6B | Windchase | 20 | +3 | 800 | one | Dark |  |

Old Sword is the game's opening weapon; a story event upgrades every Old Sword you
own (equipped or in the bag) into Heaven. Heaven and Moonblade are the "two
that are one" of the plot and cannot be bought.

### Blades (刀)

| Id | Name | Atk | Agi | Price | Hands | Element | Notes |
|---|---|---|---|---|---|---|---|
| $6C | Moonblade | 30 | +5 | 0 | one | Water | story weapon |
| $6D | Knife | 3 | +0 | 40 | one | - |  |
| $6E | Iron Sbr | 6 | -1 | 150 | one | - |  |
| $6F | Brass Sbr | 8 | -1 | 380 | one | - |  |
| $70 | Steel Sbr | 12 | -2 | 500 | one | Fire |  |
| $71 | Nether | 0 | +0 | 500 | one | Ghost | placeholder, never sold (see notes) |
| $72 | Falchion | 10 | -3 | 500 | two | Water |  |
| $73 | Tiger Sbr | 12 | -3 | 800 | two | Dark, Stone |  |
| $74 | Zigan | 20 | -4 | 900 | two | Ghost |  |

### Staves (棍) — all two-handed, reach weapons

| Id | Name | Atk | Agi | Price | Hands | Element | Notes |
|---|---|---|---|---|---|---|---|
| $75 | Cudgel | 3 | -1 | 60 | two | - |  |
| $76 | Iron Rod | 6 | -2 | 120 | two | - |  |
| $77 | Brass Rod | 8 | -3 | 250 | two | - |  |
| $78 | Tiger Rod | 12 | -4 | 600 | two | Dark |  |
| $79 | Snake Rod | 0 | +0 | - | two | Snake | placeholder, never sold (see notes) |
| $7A | Wyrm Rod | 15 | -3 | 800 | two | Lightning |  |

### Spears (槍) — reach weapons; two-handed except Javelin

| Id | Name | Atk | Agi | Price | Hands | Element | Notes |
|---|---|---|---|---|---|---|---|
| $7B | Javelin | 4 | -1 | 85 | one | - |  |
| $7C | Iron Pike | 7 | -2 | 150 | two | - |  |
| $7D | Longpike | 10 | -3 | 350 | two | - |  |
| $7E | Twin Pike | 12 | -3 | 900 | two | Stone |  |
| $7F | Silver | 0 | +0 | - | two | Lightning | placeholder, never sold (see notes) |
| $80 | Phoenix | 15 | -3 | 950 | two | Fire |  |

### Axes (斧)

| Id | Name | Atk | Agi | Price | Hands | Element | Notes |
|---|---|---|---|---|---|---|---|
| $81 | Hand Axe | 8 | -2 | 180 | one | - |  |
| $82 | Iron Axe | 11 | -3 | 400 | one | - |  |
| $83 | Brass Axe | 12 | -4 | 600 | one | - |  |
| $84 | Great Axe | 15 | -6 | 1000 | two | Stone |  |
| $85 | Giant Axe | 0 | +0 | - | one | Stone | placeholder, never sold (see notes) |
| $86 | Sky Axe | 20 | -7 | 1500 | one | Lightning |  |

### Bows (弓) — all two-handed, reach weapons

| Id | Name | Atk | Agi | Price | Hands | Element | Notes |
|---|---|---|---|---|---|---|---|
| $87 | Bamboo | 5 | -1 | 200 | two | - |  |
| $88 | Hide Bow | 10 | -2 | 450 | two | - |  |
| $89 | Crossbow | 11 | -3 | 250 | two | - |  |
| $8A | Warbow | 14 | -5 | 700 | two | - |  |
| $8B | Guanyun | 16 | -6 | 900 | two | Dark, Stone |  |
| $8C | Longshot | 0 | +0 | - | two | - | placeholder, never sold (see notes) |

---------------------------------------------------------------------------

## [7] ARMOR BY TYPE

Def adds straight to the character's Def; Agi is the speed penalty or bonus.
No piece of armor has any effect beyond these two numbers — nothing changes the
encounter rate, walking speed or resistances. Shields cannot be worn with a
two-handed weapon.

### Head (頭部)

| Id | Name | Def | Agi | Price | Notes |
|---|---|---|---|---|---|
| $8E | Straw Hat | 1 | +0 | 15 |  |
| $8F | Cloth Cap | 2 | +0 | 40 |  |
| $90 | Hide Cap | 3 | +0 | 80 |  |
| $91 | Fine Cap | 2 | +0 | 50 |  |
| $92 | Iron Helm | 6 | -1 | 150 |  |
| $93 | BrassHelm | 8 | -1 | 250 |  |
| $94 | Warlord | 0 | +0 | - | placeholder, never sold (see notes) |
| $95 | Whitebird | 12 | +1 | 500 |  |
| $96 | Sunrise | 16 | -2 | 900 |  |
| $97 | Star Helm | 13 | -1 | 1000 |  |

### Body (身體)

| Id | Name | Def | Agi | Price | Notes |
|---|---|---|---|---|---|
| $98 | Training | 1 | +0 | 30 |  |
| $99 | Hemp Robe | 1 | +0 | 40 |  |
| $9A | Feathers | 4 | +2 | 300 |  |
| $9B | Rattan | 5 | +0 | 120 |  |
| $9C | Hide Mail | 7 | -1 | 180 |  |
| $9D | Iron Mail | 12 | -2 | 360 |  |
| $9E | BrassMail | 15 | -2 | 450 |  |
| $9F | Chainmail | 18 | -2 | 600 |  |
| $A0 | Gilt Mail | 0 | +0 | - | placeholder, never sold (see notes) |
| $A1 | Bright | 24 | -3 | 1000 |  |
| $A2 | Dragon | 22 | -2 | 1300 |  |
| $A3 | Gilt Mail | 25 | +0 | 1500 |  |

The two "Gilt Mail" entries share a name; $A3 is the real one (Def 25, the best
body armor), $A0 is the placeholder.

### Shields (手持)

| Id | Name | Def | Agi | Price | Notes |
|---|---|---|---|---|---|
| $A4 | Buckler | 3 | -1 | 100 |  |
| $A5 | Targe | 5 | +0 | 180 |  |
| $A6 | Iron Shld | 10 | -2 | 300 |  |
| $A7 | BrassShld | 14 | -2 | 500 |  |
| $A8 | Bolt Shld | 15 | -3 | 1000 |  |
| $A9 | TigerShld | 20 | -3 | 1200 |  |
| $AA | CloudShld | 24 | -2 | 1300 |  |
| $AB | Moonshld | 0 | +0 | - | placeholder, never sold (see notes) |

### Hands (手部)

| Id | Name | Def | Agi | Price | Notes |
|---|---|---|---|---|---|
| $AC | Gloves | 1 | +0 | 25 |  |
| $AD | HideCuffs | 3 | +0 | 150 |  |
| $AE | ClawCuffs | 5 | +0 | 250 |  |
| $AF | IronCuffs | 8 | +0 | 400 |  |
| $B0 | SilkCuffs | 10 | +0 | 600 |  |
| $B1 | YangCuffs | 12 | +0 | 800 |  |
| $B2 | Cloudcuff | 0 | +0 | - | placeholder, never sold (see notes) |

### Feet (腳部) — the only slot that adds speed

| Id | Name | Def | Agi | Price | Notes |
|---|---|---|---|---|---|
| $B3 | Sandals | 1 | +1 | 50 |  |
| $B4 | ClothShoe | 3 | +3 | 200 |  |
| $B5 | Hide Boot | 6 | +5 | 300 |  |
| $B6 | Courtshoe | 5 | +2 | 400 |  |
| $B7 | Spikeshoe | 10 | +1 | 600 |  |
| $B8 | Riders | 15 | +6 | 1000 |  |
| $B9 | Leapers | 18 | +8 | 1200 |  |
| $BA | Trackers | 0 | +0 | - | placeholder, never sold (see notes) |
| $BB | Wingboots | 14 | +10 | 1800 |  |

---------------------------------------------------------------------------

## [8] ARTS — SKILLS (KP)

Arts are learned by **using a manual on a character** from the item menu. The
manual is consumed, the art is added to that character's list for good, and a
second copy is refused. There is no level requirement and no per-character
restriction on Skills. A character can know up to 64 arts.

Skills cost KP. Weapon skills show up in the battle Arts menu only while a
weapon of that type is equipped (the "Wrong weapon" message exists but cannot
be reached in normal play because the menu already hides them). Power is the
user's **base** Atk plus the bonus — the equipped weapon's Atk does not count,
which is why a weak weapon with a strong skill still hits hard.

| Id | Name | KP | Weapon | Target | Effect | Element |
|---|---|---|---|---|---|---|
| $C1 | Elements | 2 | any | 1 enemy | +6 power | Water, Stone |
| $C4 | Gold Hand | 8 | any | 1 enemy | +13 power | Holy, Stone |
| $C6 | Mercy | 6 | any | 1 enemy | +10 power | Holy, Stone |
| $C7 | Myriad | 12 | any | 1 enemy | +18 power | Lightning, Stone |
| $C9 | Meteor | 3 | Sword | 1 enemy | +7 power | Fire |
| $CA | Six Ways | 7 | Sword | 1 enemy | +12 power | Holy |
| $CC | Dragonswd | 13 | Sword | 1 enemy | +19 power | Fire |
| $CD | HeavenSwd | 20 | Sword | 1 enemy | +27 power | Fire, Lightning |
| $CF | Bagua | 4 | Blade | 1 enemy | +8 power | Holy |
| $D1 | Shadow | 9 | Blade | 1 enemy | +14 power | Ghost |
| $D2 | Night War | 17 | Blade | 1 enemy | +24 power | Dark |
| $D3 | Roamer | 24 | Blade | 1 enemy | +32 power | Fire, Lightning |
| $D5 | Immortals | 5 | Staff | 1 enemy | +9 power | Holy |
| $D6 | Windfire | 21 | Staff | 1 enemy | +28 power | Fire |
| $D7 | TigerTame | 12 | Staff | 1 enemy | +18 power | Dark, Stone |
| $D9 | Cross | 9 | Spear | 1 enemy | +14 power | Lightning |
| $DB | Gatebreak | 13 | Spear | 1 enemy | +19 power | Dark |
| $DC | Wyrm Pike | 22 | Spear | 1 enemy | +30 power | Fire, Water |
| $DE | Storm Axe | 31 | Axe | 1 enemy | +37 power | Lightning |
| $DF | WarlordAx | 16 | Axe | 1 enemy | +23 power | Stone |
| $E0 | Lifetaker | 22 | Axe | 1 enemy | +30 power | Ghost, Dark |
| $E2 | Piercer | 8 | Bow | 1 enemy | +13 power | Stone |
| $E3 | ChainShot | 19 | Bow | 1 enemy | +26 power | Holy |
| $E4 | Sunshot | 26 | Bow | 1 enemy | +34 power | Fire, Lightning |

Reading the table: the axe and bow lines have the biggest numbers, and Storm Axe
(+37 for 31 KP) is the strongest single-target art in the game. The any-weapon
skills (Elements, Mercy, Gold Hand, Myriad) are the ones to give Caiyi or Qiu.

---------------------------------------------------------------------------

## [9] ARTS — MAGIC (MP)

Magic costs MP. **Fang, Furong and Nameless cannot learn Magic** — using a Magic
manual on them is refused and the book is kept. "Field" marks spells castable
from the menu outside battle. Attack spells use the same power rule as Skills
(base Atk + bonus). Buffs marked "for the battle" set a flag that is cleared
when the fight ends, and casting them twice does nothing extra.

| Id | Name | MP | Field | Target | Effect | Element |
|---|---|---|---|---|---|---|
| $C2 | God's Eye | 10 | no | 1 enemy | Shows the target's HP and SP; no damage | - |
| $C3 | Sealing | 12 | no | 1 enemy | Sets the target's SP to 0 so it can no longer use arts; no damage | - |
| $C5 | Dazzle | 8 | no | 1 enemy | +18 power, and the target's next action is forced to a plain attack | - |
| $C8 | Dark Robe | 12 | no | 1 ally | Barrier: the next 3 enemy attacks on the ally do no damage | - |
| $CB | Rousing | 15 | no | 1 ally | No effect found in code (animation only) | - |
| $CE | Eclipse | 15 | no | 1 enemy | Drain: target HP/4 x (1..16)/16, max 999 | Dark |
| $D0 | SoulTheft | 25 | no | 1 enemy | As Eclipse, and heals the caster by the damage dealt | Dark |
| $D4 | Slumber | 5 | no | 1 enemy | Resets the target's turn gauge to 0 (it loses its next turn); no damage | - |
| $D8 | SlowShade | 6 | no | 1 enemy | Target speed -25% for the battle; no damage | - |
| $DA | Transmute | 10 | yes | 1 ally | Heals the ally to full HP at 1 coin per HP (limited by your money) | - |
| $E6 | FlyStone | 3 | no | 1 enemy | +12 power | Stone |
| $E8 | Holy Fire | 4 | no | 1 enemy | +14 power | Fire |
| $E9 | WaterWyrm | 5 | no | 1 enemy | +16 power | Water |
| $EA | Centipede | 7 | no | 1 enemy | +18 power | Venom |
| $EB | Wraith | 8 | no | 1 enemy | +20 power | Ghost |
| $EC | Skybolt | 15 | no | 1 enemy | +32 power | Lightning |
| $EE | Soulfall | 12 | no | 1 enemy | +25 power | Dark |
| $F0 | Net Sword | 12 | no | 1 enemy | +27 power | Holy |
| $F1 | Sage Art | 17 | no | 1 enemy | +28 power | Holy |
| $F2 | Sky Sever | 25 | no | all enemies | +30 power | Lightning |
| $F3 | EarthRend | 29 | no | all enemies | +32 power | Fire |
| $F4 | Frost | 35 | no | all enemies | +35 power | Water |
| $F5 | Windhowl | 10 | no | all enemies | +25 power | Lightning, Dark, Stone |
| $F6 | Spirit | 4 | yes | 1 ally | Heals 50 HP | - |
| $F7 | Chi Guide | 0 | no | - | Unused dummy entry (cost 0, no effect) | - |
| $F8 | MercyHymn | 8 | yes | 1 ally | Heals 150 HP and 80 KP | - |
| $F9 | Med Chant | 10 | yes | 1 ally | Heals half of max HP and cures poison and venom | - |
| $FA | WardChant | 5 | no | 1 ally | Def +50% for the battle | - |
| $FB | Whirlwind | 3 | no | 1 ally | Turn speed +50% for the battle | - |
| $FC | RosyLight | 5 | no | 1 ally | Atk +50% for the battle | - |
| $FD | WhiteBird | 10 | yes | 1 ally | Cures poison and venom | - |
| $FE | Illusion | 10 | no | 1 ally | Half of all enemy attacks on the ally miss for the battle | - |
| $FF | Vanishing | 18 | no | 1 ally | Barrier against the next 6 enemy attacks, plus Def +50% | - |

Notes:
- **Sealing** (from the teacher in Yongjiang, 400/500/600 coins — the price
  only changes his speech) empties the enemy's art pool; enemies then only use
  plain attacks. Bosses with 255 SP take one cast like anyone else.
- **Slumber** fails with "Fizzled!" in one scripted fight (group $31, the second
  Demon King phase).
- **Transmute** is a full heal paid in coins, 1 per HP; if you are short it
  heals what you can afford.
- **Dark Robe** and **Vanishing** are hit counters: the barrier absorbs whole
  attacks, and the attack that uses up the last charge does half damage.
- **Rousing** ($CB) has no effect in the code — the buff branch it was meant to
  reach is unreachable. Don't pay 500 for it.
- **Chi Guide** ($F7) is an empty entry (cost 0, no handler). Never shown.
- Enemies use these same arts from their own handler table; the enemy version of
  a healing or barrier spell is usually "full self-heal" or "sleep", see [11].

---------------------------------------------------------------------------

## [10] ARTS — INNER AND LIGHT MANUALS

Passive. Reading one adds permanently to the character's base stats and is then
listed as a known art (so it can be read once per character). They never appear
in the battle menu. Fang, Furong and Nameless can read them.

| Id | Name | Kind | Effect |
|---|---|---|---|
| $DD | Origin | Inner (內功) | Permanent +1 Atk, +2 Def, +1 Agi |
| $E1 | Taiji | Inner (內功) | Permanent +3 Atk, +2 Def, +1 Agi |
| $E5 | SevenStar | Inner (內功) | Permanent +2 Atk, +1 Def, +2 Agi |
| $E7 | Xingyi | Inner (內功) | Permanent +1 Atk, +1 Def, +1 Agi |
| $ED | Glide | Light (輕功) | Permanent +1 Atk, +1 Def, +3 Agi |
| $EF | WyrmStep | Light (輕功) | Permanent +2 Atk, +2 Def, +5 Agi |

WyrmStep is the only way besides boots to raise Agi meaningfully.

### Where arts come from *(as told in the dialogue script; partial, towns not traced)*

| Art | Source in the script |
|---|---|
| Elements | a householder sells it for 100 coins ("a friend of Amu" gets no discount) |
| Dazzle (Dazzling Eye) | Yongjiang herb counter, 500; also a Shangguan NPC for 300 |
| Sealing | Hong Mingcheng, the sealing-arts teacher, 400 / 500 / 600 (same art at every price) |
| Slumber | Water City shop, 500; also a peddler for 250 |
| Dark Robe (Demon Cloak) | Lotus Flat shop, 500 |
| Rousing / MercyHymn (Compassion) | an apothecary's back counter: 500 / 2000 |
| FlyStone (Flying Stone) | a book a guest left behind; its finder hands it over |
| Transmute (Transmuting Art) | given by an NPC after an event |
| Windfire (Wind and Fire) | given after an event |
| Gatebreak | sold under the counter by a nervous NPC ("don't say I sold it to you") |
| Bagua (Eight Trigram) | a family heirloom, given |
| Myriad | on a shelf; taking it draws "that manual's worth 500 coins" |
| SlowShade (Slow Shadow) | inside the Painting item |
| SoulTheft (Soul Art), Med Chant | event rewards |
| Sky Sever, EarthRend, Frost — "the three great arts" | the three array manuals, late-game event rewards |
| a bow manual | "a bookish man's family archery manual", given for ridding a place of a villain |
| an axe manual | found in a chest |

---------------------------------------------------------------------------

## [11] BESTIARY

All 71 enemy records, in id order. **Lv** is not a level in the usual sense: it
gates whether the enemy uses its arts at all. Let h = (Hao's level − 1) / 2.
An enemy casts nothing while h + 1 < Lv + 1, 12.5 % of the time when h + 1 =
Lv + 1, 25 % when h = Lv + 1, and 50 % once h is past it. The bar drops as Hao
grows: from Hao level 15 the enemy's Lv counts half, from 19 a quarter, and
**from Hao level 23 every enemy with arts casts at the full 50 %**. Below Hao
level 3 no enemy ever casts. **SP** is the enemy's one art pool. **Drop** is per
encounter group; for single-enemy fights it is per enemy, and a multi-enemy
version of the same group uses the same drop. Every living party member gets
the full EXP.

| Id | Name | HP | Atk | Def | Agi | SP | Lv | EXP | Coins | Arts | Drop (chance) | Affinity |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| $10 | Eye Bug | 30 | 10 | 10 | 15 | 20 | 1 | 1 | 5 | Slumber | Herb (19%) | Weak: Fire, Water, Stone |
| $11 | Bully | 35 | 11 | 10 | 16 | 30 | 2 | 2 | 5 | Elements | Herb (19%) | Weak: Fire, Lightning, Axe/Bow |
| $12 | Bandit | 40 | 11 | 10 | 16 | 30 | 2 | 2 | 2 | God's Eye | Herb (19%) | Weak: Lightning, Axe/Bow |
| $13 | Desperado | 50 | 12 | 10 | 17 | 99 | 3 | 3 | 4 | Sealing | Chi Dust (19%) | Weak: Fire, Lightning, Staff/Spear |
| $14 | Drifter | 60 | 13 | 10 | 18 | 88 | 4 | 4 | 6 | FlyStone | Chi Dust (19%) | Weak: Fire, Staff/Spear |
| $15 | Beggar | 60 | 12 | 10 | 17 | 0 | 3 | 3 | 1 | - | Herb (19%) | Weak: Fire, Sword/Blade, Axe/Bow |
| $16 | Daoist | 80 | 16 | 15 | 20 | 40 | 5 | 5 | 8 | Centipede, Skybolt | Sage Ward (100%) | Weak: Lightning, Stone, Axe/Bow; Resists: Holy, Ghost |
| $17 | Squire Li | 300 | 15 | 12 | 18 | 0 | 6 | 12 | 300 | - | Samadhi (100%) | Weak: Fire, Lightning, Ghost, Stone, Sword/Blade, Axe/Bow |
| $18 | Burrow Rat | 70 | 12 | 13 | 17 | 0 | 3 | 3 | 5 | - | Angelica (19%) | Weak: Fire, Lightning, Staff/Spear |
| $19 | Horned Ox | 150 | 18 | 10 | 17 | 0 | 5 | 5 | 8 | - | Angelica (19%) | Weak: Fire, Sword/Blade, Axe/Bow |
| $1A | Fang Tiger | 160 | 19 | 10 | 21 | 50 | 6 | 6 | 20 | Holy Fire | Samadhi (12%) | Weak: Fire, Lightning, Stone, Staff/Spear |
| $1B | Fan Hare | 40 | 11 | 10 | 17 | 0 | 2 | 2 | 10 | - | Clover (19%) | Weak: Fire, Stone, Sword/Blade, Axe/Bow |
| $1C | Tripod Asp | 60 | 13 | 10 | 19 | 40 | 4 | 4 | 6 | Slumber | Goldroot (19%) | Weak: Fire, Snake, Sword/Blade, Axe/Bow |
| $1D | Bigmouth | 400 | 18 | 10 | 21 | 25 | 9 | 10 | 30 | Slumber, Spirit | Restore (19%) | Weak: Lightning, Axe/Bow |
| $1E | Two-Face | 100 | 16 | 10 | 20 | 20 | 5 | 5 | 8 | Spirit | Angelica (19%) | Weak: Fire, Lightning, Staff/Spear |
| $1F | Wyrmsting | 80 | 13 | 10 | 17 | 60 | 4 | 4 | 8 | WaterWyrm | Angelica (19%) | Weak: Fire, Snake, Axe/Bow |
| $20 | Great Eye | 120 | 14 | 10 | 19 | 0 | 5 | 6 | 8 | - | Angelica (19%) | Weak: Lightning, Axe/Bow, Staff/Spear |
| $21 | Silkdancer | 150 | 18 | 10 | 20 | 65 | 7 | 7 | 20 | Wraith | Angelica (19%) | Weak: Fire, Stone, Sword/Blade |
| $22 | Drum Ghost | 250 | 18 | 10 | 20 | 115 | 6 | 6 | 20 | Skybolt | GhostWard (12%) | Weak: Lightning, Dark, Holy, Staff/Spear; Resists: Ghost |
| $23 | Whipdancer | 300 | 20 | 10 | 20 | 0 | 7 | 7 | 12 | - | Restore (19%) | Weak: Lightning, Ghost, Stone |
| $24 | Fire Eater | 400 | 22 | 10 | 22 | 115 | 10 | 9 | 18 | Holy Fire | Samadhi (12%) | Weak: Water, Dark, Holy, Axe/Bow, Staff/Spear; Resists: Fire |
| $25 | Juggler | 300 | 18 | 10 | 20 | 0 | 8 | 8 | 14 | - | Angelica (19%) | Weak: Lightning, Venom, Axe/Bow; Resists: Water, Ghost |
| $26 | Dancer | 200 | 16 | 10 | 21 | 35 | 7 | 7 | 12 | Spirit, Slumber | Angelica (19%) | Weak: Lightning, Venom, Dark, Holy, Staff/Spear; Resists: Ghost |
| $27 | Centaur | 200 | 21 | 20 | 22 | 40 | 12 | 10 | 24 | Wraith, Spirit | Samadhi (12%) | Weak: Water, Holy; Resists: Ghost |
| $28 | Brass Mask | 150 | 18 | 15 | 21 | 0 | 9 | 8 | 16 | - | Angelica (19%) | Weak: Fire, Lightning, Holy, Axe/Bow; Resists: Ghost |
| $29 | Masked Man | 250 | 18 | 10 | 21 | 160 | 9 | 8 | 16 | Slumber | Angelica (19%) | Weak: Water, Lightning, Sword/Blade |
| $2A | Cat Mask | 300 | 19 | 10 | 21 | 0 | 10 | 9 | 18 | - | Angelica (19%) | Weak: Fire, Holy, Sword/Blade; Resists: Ghost |
| $2B | Snakehead | 250 | 18 | 10 | 20 | 0 | 8 | 8 | 14 | - | Goldroot (100%) | Weak: Holy, Snake |
| $2C | Flower Fay | 420 | 21 | 10 | 24 | 25 | 12 | 10 | 24 | Spirit, Slumber | Datura (19%) | Weak: Fire, Holy; Resists: Water |
| $2D | Goat Demon | 1150 | 32 | 12 | 24 | 160 | 18 | 13 | 50 | Sealing, Skybolt | Bolt Ward (19%) | Weak: Stone; Resists: Water, Ghost, Fire |
| $2E | Tuoluo | 1450 | 29 | 12 | 24 | 150 | 20 | 14 | 60 | Centipede | Diamond (19%) | Weak: Venom, Ghost, Staff/Spear; Resists: Holy |
| $2F | Sky Grief | 1800 | 31 | 10 | 25 | 0 | 22 | 15 | 70 | - | Angelica (19%) | Weak: Lightning, Axe/Bow; Resists: Ghost |
| $30 | Sky Demon | 2000 | 31 | 10 | 25 | 0 | 22 | 15 | 70 | - | Samadhi (12%) | Weak: Holy, Staff/Spear; Resists: Water |
| $31 | Void | 2500 | 33 | 10 | 26 | 105 | 24 | 16 | 80 | Spirit, Skybolt | Angelica (19%) | Weak: Holy, Staff/Spear; Resists: Ghost |
| $32 | Gate Demon | 3000 | 33 | 10 | 26 | 165 | 24 | 16 | 80 | Wraith, Sealing | Angelica (19%) | Weak: Fire, Water; Resists: Ghost |
| $33 | Doom | 3200 | 36 | 10 | 27 | 0 | 27 | 18 | 100 | - | Angelica (19%) | Weak: Stone, Axe/Bow; Resists: Ghost |
| $34 | Abbot | 500 | 17 | 12 | 21 | 0 | 8 | 8 | 200 | - | Elixir (100%) | Weak: Fire, Snake; Resists: Holy, Ghost |
| $35 | Mantis Asp | 1000 | 20 | 10 | 21 | 0 | 11 | 10 | 200 | - | Realgar (100%) | Weak: Snake; Resists: Holy, Ghost |
| $36 | Dark Lady | 1000 | 20 | 12 | 21 | 0 | 11 | 10 | 1000 | - | GhostWard (100%) | Weak: Fire, Sword/Blade |
| $37 | Darkroach | 3000 | 23 | 10 | 22 | 105 | 14 | 11 | 3000 | Slumber, Slumber | Bolt Ward (100%) | Weak: Fire, Axe/Bow |
| $38 | Green Maid | 400 | 25 | 10 | 23 | 0 | 7 | 20 | 100 | - | Samadhi (100%) | Weak: Fire, Sword/Blade; Resists: Ghost |
| $39 | Red Maid | 400 | 16 | 10 | 28 | 0 | 7 | 20 | 100 | - | Samadhi (100%) | Weak: Lightning, Stone; Resists: Ghost |
| $3A | Gold Maid | 400 | 16 | 15 | 23 | 0 | 7 | 20 | 100 | - | Samadhi (100%) | Weak: Holy, Axe/Bow; Resists: Ghost |
| $3B | Pool Fiend | 2200 | 32 | 15 | 25 | 0 | 22 | 30 | 200 | - | Mica Cap (100%) | Weak: Fire, Snake; Resists: Water, Ghost |
| $3C | Mtn Spirit | 10000 | 62 | 10 | 30 | 255 | 52 | 500 | 1000 | - | Dragoncap (100%) | Weak: Lightning; Resists: Holy, Water, Fire |
| $3D | Sky Demon | 20000 | 70 | 6 | 32 | 255 | 82 | 500 | 2000 | - | Ginseng (100%) | Weak: Venom, Dark; Resists: Ghost |
| $3E | Hong | 999 | 26 | 10 | 25 | 255 | 17 | 25 | 0 | - | Ginseng (100%) | - |
| $3F | Earthdemon | 10000 | 65 | 20 | 30 | 255 | 102 | 50 | 0 | - | Ginseng (100%) | - |
| $40 | Demon King | 20000 | 75 | 30 | 28 | 255 | 255 | 0 | 0 | - | Herb (100%) | Weak: Venom, Stone, Axe/Bow |
| $41 | Demon King | 60000 | 80 | 35 | 35 | 255 | 255 | 0 | 0 | - | Herb (100%) | - |
| $42 | Demon King | 60000 | 60 | 20 | 30 | 255 | 255 | 0 | 0 | - | Herb (100%) | Weak: Fire, Water, Venom, Dark, Holy, Sword/Blade, Staff/Spear |
| $43 | Fiend | 250 | 20 | 10 | 21 | 20 | 9 | 8 | 20 | Slumber | Samadhi (12%) | Weak: Fire, Holy; Resists: Water, Ghost |
| $44 | Novice | 150 | 16 | 15 | 21 | 25 | 6 | 12 | 10 | Spirit, Elements | Herb (19%) | Weak: Ghost; Resists: Holy |
| $45 | Servant | 120 | 14 | 10 | 19 | 60 | 5 | 5 | 10 | Elements, God's Eye | Herb (100%) | Weak: Stone, Axe/Bow |
| $46 | Fungus | 30 | 10 | 10 | 15 | 0 | 1 | 30 | 100 | - | Herb (19%) | Weak: Fire; Resists: Water |
| $47 | Stone Imp | 150 | 16 | 20 | 20 | 0 | 7 | 15 | 50 | - | Rock Ward (12%) | Weak: Lightning, Stone |
| $48 | Snake King | 420 | 25 | 10 | 25 | 10 | 12 | 10 | 24 | Dragonswd | Ice Pill (31%) | Weak: Snake |
| $49 | Wind Demon | 50 | 15 | 25 | 20 | 40 | 6 | 10 | 0 | Skybolt | Herb (19%) | Weak: Water |
| $4A | Venom Star | 350 | 12 | 10 | 17 | 50 | 3 | 3 | 20 | Slumber | Goldroot (19%) | Weak: Fire; Resists: Water |
| $4B | Fire Child | 120 | 20 | 15 | 22 | 170 | 6 | 10 | 20 | Holy Fire | Angelica (19%) | Weak: Water; Resists: Fire |
| $4C | Snow Fiend | 120 | 25 | 10 | 20 | 40 | 6 | 8 | 15 | Sealing, WaterWyrm | Herb (19%) | Weak: Fire |
| $4D | Tusk Fiend | 60 | 13 | 10 | 23 | 65 | 4 | 4 | 12 | Slumber, Centipede | Goldroot (25%) | Weak: Fire, Water, Axe/Bow |
| $4E | Cactus | 80 | 14 | 10 | 19 | 40 | 5 | 5 | 12 | Slumber, Sealing | Herb (19%) | Weak: Fire; Resists: Water |
| $4F | Soul Envoy | 1500 | 38 | 10 | 24 | 190 | 19 | 12 | 55 | Wraith, Wraith | Samadhi (12%) | Weak: Holy; Resists: Ghost |
| $50 | Left Grd | 4000 | 42 | 10 | 25 | 0 | 32 | 20 | 0 | - | - | - |
| $51 | Right Grd | 3500 | 45 | 10 | 25 | 0 | 35 | 20 | 0 | - | - | - |
| $52 | ??? | 9999 | 20 | 99 | 20 | 0 | 99 | 1000 | 0 | - | Herb (100%) | - |
| $53 | Earth Imp | 20000 | 50 | 20 | 32 | 255 | 82 | 500 | 2000 | - | Ginseng (100%) | Weak: Holy, Sword/Blade |
| $54 | Elixir Imp | 3000 | 45 | 20 | 24 | 100 | 25 | 12 | 55 | Dragonswd, Slumber | Samadhi (100%) | Weak: Water, Holy; Resists: Ghost |
| $55 | Demoness | 2000 | 45 | 10 | 24 | 100 | 25 | 12 | 55 | Wraith, Wraith | Samadhi (100%) | Weak: Fire, Holy; Resists: Ghost |
| $56 | Court Danc | 2500 | 45 | 15 | 26 | 0 | 25 | 12 | 55 | - | Samadhi (100%) | Weak: Stone, Axe/Bow |

Reading the table:
- Enemy arts: Spirit = full self-heal (only when hurt). Slumber, Dazzle, Sealing
  and most support spells = your character loses its next turn ("sleep").
  Dragonswd and Centipede from an enemy inflict poison (Dragonswd: poison and
  venom). Holy Fire / WaterWyrm / Wraith / Skybolt are +14 / +16 / +20 / +32
  attacks. Anything else = a generic +12 three-hit.
- Squire Li, the Abbot, the Maids and Dark Lady are story fights with 100 %
  drops and big coin rewards.
- The three **Demon King** rows are the three phases of the final boss (chained
  by code); they give no EXP or coins. Sky Demon $3D (20,000 HP) and Earthdemon /
  Earth Imp (10,000 / 20,000) are the late bosses; Mtn Spirit (10,000 HP, 500
  EXP) is the "山魅" of the prologue. ??? ($52) has 9,999 HP and Def 99 and is
  worth 1,000 EXP — it appears only as a pack of five in the Dunhuang area.
- **Hong ($3E), Left Grd ($50) and Right Grd ($51)** exist in the table but are
  in no encounter group: unused.

---------------------------------------------------------------------------

## [12] ENCOUNTER TABLES

Overworld: the game picks the nearest of 19 region centres to your tile, then a
list by terrain. From hero level 3 a fight has a 7/16 chance of being the
multi-enemy version of the group, 11/16 from level 5. At level 1–2 every fight
is a single enemy. Percentages below are the roll weights.

| Region (centre tile) | Encounters |
|---|---|
| R00 (140,140) start | Eye Bug 40, Bully 30, Bandit 30 |
| R01 (136,128) | Eye Bug 30, Bully 30, Bandit 20, Beggar 20 |
| R02 (139,105) | Eye Bug 10, Bully 15, Bandit 15, Desperado 20, Drifter 20, Beggar 20 |
| R03 (144,94) | Desperado 30, Drifter 30, Beggar 20, Fan Hare 20 (on rough ground Cactus 35 replaces some) |
| R04 (125,83) | Drifter 40, Beggar 30, Fan Hare 30 (rough: Cactus 35; water side: Two-Face 30) |
| R05 (120,61) | Burrow Rat 25, Horned Ox 15, Fang Tiger 10, Tripod Asp 15, Two-Face 15, Wyrmsting 20 |
| R06 (124,49) | Burrow Rat 15, Horned Ox 15, Fang Tiger 20, Two-Face 15, Wyrmsting 15, Great Eye 20 |
| R07 (121,25) | Bigmouth 10, Two-Face 25, Great Eye 25, Fire Eater 10, Brass Mask 30 |
| R08 (104,13) | Bigmouth 30, Fire Eater 25, Dancer 25, Brass Mask 20 |
| R09 (67,34) | Masked Man 25, Cat Mask 25, Flower Fay 25, Snow Fiend 25 |
| R10 (64,47) | Masked Man 15, Cat Mask 20, Flower Fay 25, Centaur 25, Snow Fiend 15 |
| R11 (61,83) | Centaur 25, Flower Fay 25, Goat Demon 30, Snow Fiend 20 (rough: Fiend 25) |
| R12 (70,115), R13 (61,121) | Goat Demon 10, Snake King 45, Wind Demon 45 (rough: Fiend 40) |
| R14 (43,119) | Goat Demon 20, Tuoluo 25, Sky Grief 25, Wind Demon 30 |
| R15 (31,103) | Sky Grief 40, Sky Demon 40, Fungus 5, Wind Demon 10, Soul Envoy 5 |
| R16 (22,98) | packs: Flower Fay+Void+Goat Demon 30, Goat Demon×2+Sky Demon 30; Void 10, Sky Demon 10, Fungus 5, Soul Envoy 15 |
| R17 (14,32) endgame | Doom 50, Soul Envoy 45, Fungus 5 |
| R18 (92,115) | Goat Demon 10, Snake King 35, Fungus 20, Wind Demon 35 (rough: Fiend 20) |

Dungeon maps use their own lists:

| List | Encounters |
|---|---|
| M1 (early caves) | Desperado 20, Drifter 25, Tripod Asp 20, Stone Imp 10, Tusk Fiend 25 |
| M2 (Water City floors) | Tripod Asp 10, Great Eye 10, Silkdancer 10, Drum Ghost 10, Whipdancer 15, Juggler 15, Stone Imp 15, Tusk Fiend 15 |
| M3 | Silkdancer 15, Drum Ghost 15, Whipdancer 20, Fire Eater 15, Juggler 15, Centaur 20 |
| M4 | Masked Man 5, Cat Mask 10, Stone Imp 10, Centaur 25, Goat Demon 20, Tuoluo 25, Tusk Fiend 5 |
| M5 | Goat Demon 30, Snake King 10, Fire Child 5, Tuoluo 25, Sky Grief 25, Tusk Fiend 5 |
| M6 | Tuoluo 30, Sky Grief 20, Goat Demon 20, Fire Child 30 |
| M7 | Sky Demon 15, Gate Demon 25, Goat Demon 25, Fungus 10, Fire Child 25 |
| M8 (late dungeons) | Tuoluo 15, Sky Grief 15, Sky Demon 15, Void 15, Gate Demon 15, Doom 19, plus 2 each Tripod Asp / Stone Imp / Tusk Fiend |

Fungus (Fungus, 30 HP, 30 EXP, 100 coins) is the game's metal-slime: a level-1
body worth thirty times its EXP, at 5–20 % in the late overworld.

---------------------------------------------------------------------------

## [13] SHOPS AND INNS

Towns in story order. Selling returns half price everywhere.

| Town | Shop | Stock |
|---|---|---|
| Niujia | Gen. Store | Dirk, Bamboo, Straw Hat, Training, Herb, Chi Dust |
| Baidaokou | stall | Knife, Cudgel, Straw Hat, Cloth Cap, Buckler, Herb, Chi Dust |
| Shangguan | Armory (weapons) | Dirk, Iron Swd, Knife, Iron Sbr, Cudgel, Javelin, Bamboo |
| Shangguan | Armory (armor) | Straw Hat, Cloth Cap, Training, Rattan, Buckler, Gloves, Sandals |
| Shangguan | Apothecary | Herb, Chi Dust, Samadhi, Clover, Goldroot, Diamond |
| Yongjiang | Arms&Herbs (weapons) | Iron Swd, Iron Sbr, Cudgel, Iron Rod, Javelin, Hide Bow |
| Yongjiang | Armorer | Cloth Cap, Hide Cap, Rattan, Buckler, Targe, Gloves, ClothShoe |
| Yongjiang | Arms&Herbs (herbs) | Herb, Chi Dust, Samadhi, Goldroot, Diamond, Bonecap, Datura, Realgar, **Dazzle 500** |
| Fengling | Gen. Store | Hide Cap, Herb, Angelica, Chi Dust, Goldroot, Realgar, Rock Ward |
| Water City | Weapons | Iron Swd, Brass Swd, Peachwood, Brass Sbr, Iron Pike, Hand Axe, Hide Bow |
| Water City | Armorer | Hide Cap, Fine Cap, Hemp Robe, Hide Mail, Targe, HideCuffs, ClothShoe |
| Water City | Shop | Herb, Angelica, Chi Dust, Restore, Samadhi, Goldroot, Bonecap, Rock Ward, **Slumber 500** |
| Shilipu | Weapons | Brass Swd, Claymore, Brass Sbr, Falchion, Iron Rod, Hand Axe, Crossbow |
| Shilipu | Armorer | Iron Helm, Hide Mail, Iron Mail, Targe, Iron Shld, HideCuffs, Hide Boot |
| Shilipu | Shop | Herb, Angelica, Chi Dust, Restore, Goldroot, Realgar |
| Lotus Flat | Armory (weapons) | Brass Swd, Claymore, Peachwood, Falchion, Brass Rod, Longpike, Iron Axe |
| Lotus Flat | Armory (armor) | Fine Cap, Iron Helm, Hemp Robe, Hide Mail, Iron Mail, Iron Shld, Courtshoe |
| Lotus Flat | Shop | Angelica, Restore, Elixir, Samadhi, Goldroot, Bonecap, Realgar, Rock Ward, GhostWard, **Dark Robe 500** |
| Xiaoyao | Ironsmith (weapons) | Goldfish, Tianpeng, Brass Rod, Tiger Rod, Longpike, Iron Axe, Brass Axe, Crossbow |
| Xiaoyao | Ironsmith (armor) | Iron Helm, BrassHelm, BrassMail, Iron Shld, BrassShld, ClawCuffs, Hide Boot, Courtshoe |
| Xiaoyao | Craftsman | Angelica, Ginseng, Restore, Strength, Elixir, Cinnabar, GhostWard, Bolt Ward |
| Tuoketuo | Armory (weapons) | Brass Sbr, Tiger Sbr, Tiger Rod, Longpike, Twin Pike, Brass Axe, Warbow |
| Tuoketuo | Armory (armor) | BrassHelm, BrassMail, BrassShld, ClawCuffs, IronCuffs, Courtshoe, Spikeshoe |
| Tuoketuo | Shop | Angelica, Ginseng, Restore, Strength, Samadhi, Goldroot, Cinnabar, Bolt Ward, Sage Ward |
| Baifeng | House NPC | same stock as the Tuoketuo armor counter |
| Baifeng | shop, counter 1 | Goldfish, Tianpeng, Steel Sbr, Tiger Sbr, Twin Pike, Great Axe, Warbow |
| Baifeng | shop, counter 2 | BrassHelm, Feathers, BrassMail, Chainmail, BrassShld, IronCuffs, Spikeshoe |
| Baifeng | shop | Ginseng, Strength, Samadhi, Goldroot, Ice Pill, Bolt Ward, Sage Ward |

Four inventories in the ROM have no shopkeeper anywhere (unused): two more herb
lists, one with **Wingboots 1800** and Sweetbud, and the only skill-manual shop
in the data (God's Eye, Eclipse, MercyHymn, Med Chant at 500 each).

Sold in no reachable shop, so they come from chests and events: Desire, Twin
Swd, Windchase, Zigan, Wyrm Rod, Phoenix, Sky Axe, Guanyun; Whitebird, Sunrise,
Star Helm; Bright, Dragon, Gilt Mail ($A3); Bolt Shld, TigerShld, CloudShld;
SilkCuffs, YangCuffs; Riders, Leapers, Wingboots; and the story weapons Old
Sword, Heaven and Moonblade.

### Inns *(prices read from the pay command at each inn counter — inferred)*

| Town | Price |
|---|---|
| Shangguan | 10 |
| Yongjiang | 30 |
| Water City | 30 |
| Shilipu | 30 |
| Lotus Flat | 10 |
| Xiaoyao | 60 |
| Tuoketuo | 100 |

Resting refills HP and KP and clears poison. Niujia, Baidaokou and Fengling have
no inn.

---------------------------------------------------------------------------

## [14] LEVEL, EXP AND GROWTH TABLES

Each cell is **total EXP to reach the level / max HP / max KP / max MP**. Each
character has its own EXP curve (Hao, Hong and Nameless share one). Level 60
needs 65,535 EXP, which is the counter's cap, so it is the true maximum.

| Lv | Hao | Fang | Furong | Caiyi | Hong | Qiu | Humuzhu | Nameless |
|---|---|---|---|---|---|---|---|---|
| 1 | 0 / 30/16/2 | 0 / 25/20/0 | 0 / 20/14/0 | 0 / 15/10/12 | 0 / 35/18/0 | 0 / 20/12/15 | 0 / 18/12/6 | 0 / 35/16/0 |
| 2 | 8 / 32/18/4 | 12 / 27/22/0 | 10 / 22/16/0 | 15 / 17/12/14 | 8 / 37/20/2 | 13 / 23/14/17 | 12 / 20/14/7 | 8 / 38/18/0 |
| 3 | 18 / 35/20/6 | 25 / 30/24/0 | 22 / 25/18/0 | 32 / 19/13/16 | 18 / 40/23/4 | 28 / 26/16/20 | 30 / 23/16/8 | 18 / 42/21/0 |
| 5 | 60 / 42/24/10 | 80 / 37/27/0 | 75 / 32/22/0 | 90 / 25/17/21 | 60 / 47/28/8 | 90 / 33/19/25 | 90 / 30/19/12 | 60 / 51/26/0 |
| 8 | 550 / 55/32/17 | 580 / 50/32/0 | 605 / 46/28/0 | 590 / 36/22/28 | 620 / 65/37/16 | 568 / 46/25/34 | 670 / 44/25/17 | 620 / 68/35/0 |
| 10 | 1160 / 66/38/23 | 1175 / 60/36/0 | 1190 / 58/33/0 | 1170 / 45/26/33 | 1250 / 80/43/22 | 992 / 56/29/40 | 1355 / 55/29/20 | 1264 / 82/41/0 |
| 12 | 1816 / 81/44/29 | 1833 / 72/41/0 | 1841 / 72/38/0 | 1832 / 56/30/39 | 1923 / 97/50/28 | 1468 / 68/33/47 | 2106 / 68/33/24 | 1952 / 98/47/0 |
| 15 | 2904 / 107/53/38 | 2964 / 92/49/0 | 2959 / 97/47/0 | 2996 / 74/36/49 | 3033 / 128/62/38 | 2314 / 87/41/58 | 3374 / 91/40/31 | 3072 / 124/59/0 |
| 18 | 4140 / 140/65/49 | 4305 / 117/58/0 | 4270 / 126/56/0 | 4378 / 96/43/61 | 4287 / 164/74/50 | 3366 / 108/50/70 | 4843 / 117/49/38 | 4388 / 153/71/0 |
| 20 | 5060 / 165/73/57 | 5335 / 136/65/0 | 5265 / 148/62/0 | 5428 / 113/48/69 | 5216 / 190/82/58 | 4200 / 124/56/79 | 5948 / 137/55/42 | 5364 / 174/79/0 |
| 25 | 7754 / 237/95/77 | 8465 / 196/84/0 | 8234 / 214/81/0 | 8540 / 169/63/92 | 7910 / 263/106/78 | 6856 / 170/73/104 | 9209 / 196/72/57 | 8266 / 239/103/0 |
| 30 | 11110 / 326/120/99 | 12453 / 270/108/0 | 11990 / 301/101/0 | 12402 / 236/81/121 | 11228 / 352/131/103 | 10450 / 229/94/130 | 13283 / 270/92/75 | 11910 / 319/130/0 |
| 35 | 15254 / 425/150/124 | 17407 / 354/134/0 | 16658 / 406/125/0 | 17098 / 312/103/152 | 15296 / 455/161/132 | 15106 / 300/117/160 | 18296 / 355/116/95 | 16406 / 413/160/0 |
| 40 | 20304 / 545/183/152 | 23435 / 448/164/0 | 22330 / 521/151/0 | 22724 / 397/128/187 | 20240 / 581/192/162 | 20948 / 384/146/190 | 24438 / 451/142/118 | 21900 / 527/191/0 |
| 45 | 26326 / 681/218/182 | 30684 / 553/196/0 | 29062 / 649/181/0 | 29370 / 489/155/222 | 26183 / 715/227/196 | 28052 / 480/179/225 | 31824 / 557/172/143 | 28536 / 664/226/0 |
| 50 | 33376 / 831/257/215 | 39399 / 669/231/0 | 36917 / 774/215/0 | 37122 / 590/185/260 | 33216 / 854/262/231 | 36506 / 585/214/260 | 40507 / 675/205/170 | 36462 / 823/261/0 |
| 55 | 41476 / 999/300/250 | 50094 / 799/270/0 | 45996 / 899/250/0 | 46068 / 699/220/300 | 41393 / 999/300/270 | 46056 / 699/250/300 | 50572 / 799/243/200 | 45824 / 999/300/0 |
| 59 | 56000 / 999/340/288 | 61500 / 799/309/0 | 59000 / 899/288/0 | 60000 / 699/258/338 | 57000 / 999/338/309 | 59000 / 699/288/338 | 61500 / 799/277/231 | 59000 / 999/338/0 |
| 60 | 65535 / 999/350/300 | 65535 / 799/320/0 | 65535 / 899/300/0 | 65535 / 699/270/350 | 65535 / 999/350/320 | 65535 / 699/300/350 | 65535 / 799/290/240 | 65535 / 999/350/0 |

Base Atk and Def are +1 per level on top of the starting values in [2]; base
Agi never changes.

---------------------------------------------------------------------------

## [15] SECRETS, DUMMY CONTENT AND BUGS

**Debug mode.** The code checks a word in save RAM for the value `$BC42` and,
if it matches, reads controller 2 as a debug pad: P2 Start shows a hex overlay,
P2 Select steps the map number, P2 B warps to it. Nothing in the game ever
writes that value, so it is dead on a real cartridge; a cheat device (or the
MiSTer core's cheat file) can set it. A second word next to it disables music.

**Things that do nothing.**
- Reviver (900 coins, "said to raise the dead") — empty routine, greyed out.
- Peacock, Fire Ward, Red Ward, Bind Ward — consumed, no effect.
- Sage Ward and the Sage Art spell — the animation plays and no damage is done.
- Rousing (500 coins) — no effect.
- Chi Guide — empty art entry.

**Placeholders.** Ten equipment slots, one per type, are all-zero, priced 9999
and sold nowhere: Nether, Snake Rod, Silver, Giant Axe, Longshot, Warlord (helm),
Gilt Mail $A0, Moonshld, Cloudcuff, Trackers. Their element words were filled
in (Nether: Ghost, Snake Rod: Snake, Silver: Lightning, Giant Axe: Stone) but
their stats never were.

**Unused enemies:** Hong, Left Grd, Right Grd. **Unused shops:** the four in
[13], including the only skill-manual shop.

**Quirks worth knowing.**
- Damage has no random factor. If a hit does 1, it will keep doing 1 until you
  raise Atk or lower the enemy's Def (elements, poison on the enemy).
- Thrown items and arts use base Atk only — buying a better weapon does not
  make your Skills stronger, leveling does.
- The battle item menu lists everything in the bag; picking a non-battle item
  just fails and is not consumed.
- Poison never kills on the map (HP floors at 1) and persists after battle.
- EXP is not split, so a full party of four levels as fast as a solo hero.

---------------------------------------------------------------------------
