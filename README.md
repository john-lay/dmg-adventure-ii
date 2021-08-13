# DMG Adventure II
A continuation of https://github.com/john-lay/dmg-adventure built with GB Studio 2-beta4

# Technical notes

## Variable list

A listing of variables and their types in re-usable components (Actors/Scenes)

### Global
* `$00$: Variable 000` Health - `number`. (0-4 Indicates the number of hearts Zelda has)
* `$01$: Variable 001` Rupees - `number`. (Indicates the number of rupees Zelda has collected)
* `$02$: Variable 002` Scene Flags - `byte`.
  * (Flag 1 represents the enemy dropping a rupee)
  * (Flag 2 represents the enemy dropping a heart)
  * (Flag 3 represent the enemy dropped a rupee or a heart))
  * (Flag 4 represents Zelda has spoken to a fairy))
  * (Flag 5 is ???))
  * (Flag 6 is ???))
  * (Flag 7 is ???))
  * (Flag 8 is ???))
* `$03$: Variable 003` Wand Equipped - `bool`.
* `$04$: Variable 004` Spell Equipped - `byte`.
  * (Flag 1 represents Zelda has the Axe equipped - costs 1 Rupee to cast) 
  * (Flag 2 represents Zelda has the Noise spell equipped - costs 1 Rupee to cast)
  * (Flag 3 represents Zelda has the Turquoise Ring spell equipped - costs 26 Rupees to cast)
  * (Flag 4 represents Zelda has the Jade Amulet spell equipped  - costs 24 Rupees to cast)
  * (Flag 5 represents Zelda has the feather spell equipped - costs 2 Rupees to cast)
  * (Flag 6 represents Zelda has the pyros spell equipped - costs 4 Rupees to cast)
  * (Flag 7 represents Zelda has the broadsword equipped - costs 2 Rupees to cast)
  * (Flag 8 represents Zelda has the Rings of Fire equipped - costs 3 Rupees to cast)
* `$05$: Variable 005` Spell Cost - `number`. (Cost of the equipped spell)
* `$06$: Variable 006` Collectable - `byte`.
  * (Flag 1 is the Axe)
  * (Flag 2 is the Raft)
  * (Flag 3 is the Noise spell)
  * (Flag 4 is the Harp)
  * (Flag 5 is Feather)
  * (Flag 6 is Flute)
  * (Flag 7 is Pyros)
  * (Flag 8 is Broadsword)
* `$07$: Variable 007` Purchasable - `byte`.
  * (Flag 1 is the Turquoise Ring)
  * (Flag 2 is the Jade Amulet)
  * (Flag 3 is the Rings of Fire)
  * (Flag 4 is bone)
  * (Flag 5 is axe)
  * (Flag 6 is potion)
  * (Flag 7 is candle)
  * (Flag 8 is ???)
* `$08$: Variable 008` Illusion Shrine Flags - `byte`.
  * (Flag 1 is the Orb)
  * (Flag 2 is the Map)
  * (Flag 3 is the Compass)
  * (Flag 4 is key)
  * (Flag 5 is dagger)
  * (Flag 6 is represents Zelda has placed the Orb on the Pedestal)
  * (Flag 7 is represents Zelda has used the first key)
  * (Flag 8 is represents Zelda has used the second key)
* `$09$: Variable 009` Overworld Flags - `byte`.
  * (Flag 1 represents Zelda has spoken to the White Steed Lodgekeep)
  * (Flag 2 represents Zelda has spoken to Lonlyn in Verna)
  * (Flag 3 represents Zelda has completed the Illusion Shrine)
  * (Flag 4 represents Zelda has completed the Air Shrine)
  * (Flag 5 is ???)
  * (Flag 6 is ???)
  * (Flag 7 is ???)
  * (Flag 8 is ???)
* `$10$: Variable 010` Dungeon Room - `number`. (Indicates the dungeon room Zelda occupies)
* `$11$: Variable 011` Enemy Counter - `number`. (Indicates the number of Zelda has defeated in this scene)
* `$12$: Variable 012` Air Shrine Flags - `byte`.
  * (Flag 1 represents Zelda has the Calm spell equipped - costs 1 Rupee to cast)
  * (Flag 2 is the Map)
  * (Flag 3 is the Compass)
  * (Flag 4 is the Rug)
  * (Flag 5 is the Bow + Arrow)
  * (Flag 6 represents Zelda has the Bow + Arrow equipped - costs 1 Rupee to cast)
  * (Flag 7 represents Zelda has defeated the second Vapora)
  * (Flag 8 Represents Zelda has restored the bridge)
* `$13$: Variable 013` Destiny Shrine Flags - `byte`.
  * (Flag 1 represents Zelda has the Calm spell equipped - costs 1 Rupee to cast)
  * (Flag 2 is the Map)
  * (Flag 3 is the Compass)
  * (Flag 4 is ???)
  * (Flag 5 is ???)
  * (Flag 6 is ???)
  * (Flag 7 is ???)
  * (Flag 8 is ???)
  
# Dev Notes
## Encapsulation
The best way to enable reusable code components is to encapsulate the logic for a particular feature into a script.
For example the calculation to display the number of rupees is contained in the rupee counter actor which sets the hundreds, tens and units.
Other scripts can decrement the total number of rupees, but to update the UI the rupee counter actor (hundreds) script must be called.
The same is done for the health (hearts). This was done for DMG Adventure (part I) where:
- The Wand was responsible for calculating what it hit
- Enemies were responsible for calculating when they hit Zelda
- The heart / rupee collectible was responsible for dislaying the right collectable item, but it was incorrectly responsible for updating the heart and rupee counter.

# Enemy References (DMG Adventure I)
Where possible enemies have been identified in Zelda's Adventure and their conterpart has been used from Link's Awakening. When the enemy doesn't exist in Link's Awakening I've tried to carefully substitute it with an enemy that is both similar and likely to be unique to Link's Awakening. This is to prevent future iterations of the project from having collisions when I try to identify enemies later in the game and find I've already used their counterpart. \
[Enemies from Zelda's Adventure](https://zelda.gamepedia.com/Enemies_in_Zelda%27s_Adventure) \
[Enemies from Link's Awakening](https://zelda.gamepedia.com/Enemies_in_Link%27s_Awakening)


## Goriya -> Darknut
![Goriya CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/2/2d/ZA_Goriya.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/7/78/LA_Darknut_Sprite.png" alt="Darknut DMG" width="32" height="32"/>

## Tektites -> Beetle
![Tektites CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/3/32/ZA_Tektite_2.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/3/35/LA_Beetle_Sprite.png" alt="Beetle DMG" width="32" height="32"/>

## Moblin -> Moblin
![Moblin CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/9/95/ZA_Moblin.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/4/41/LA_Moblin_Sprite.png" alt="Moblin DMG" width="32" height="32"/>

## Deeler -> Spiny Beetle
![Deeler CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/5/51/ZA_Deeler_2.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/1/12/LA_Spiny_Beetle_Sprite.png" alt="Spiny Beetle DMG" width="32" height="32"/>

## Moby -> Crow
![Moby CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/6/60/ZA_Moby.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/c/c0/LA_Crow_Sprite.png" alt="Crow DMG" width="32" height="32"/>

## Leever -> Leever
![Leever CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/2/2c/ZA_OoT_Leever_Model.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/d/d4/LA_Leever_Sprite.png" alt="Leever DMG" width="32" height="32"/>

## Keese -> Keese
![Keese CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/1/1a/ZA_Keese.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/7/7e/LA_Keese_Sprite.png" alt="Keese DMG" width="32" height="32"/>

## Unknown enemy -> Zol
![Unknown CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/e/e7/ZA_Zol.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/2/22/LA_Zol_Sprite.png" alt="Zol DMG" width="32" height="32"/>

## Peahat -> Octorok
![Peahat CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/d/d1/ZA_Peahat_Sprite.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/f/f8/LA_Octorok_Sprite.png" alt="Octorok DMG" width="32" height="32"/>

## Sardak (Sheepman) -> Shrouded Stalfos
![Sardak (Sheepman) CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/6/61/Sheepman_Red_Frontal_View.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/f/fd/LA_Shrouded_Stalfos_Sprite.png" alt="Shrouded Stalfos DMG" width="32" height="32"/>

## Llort (Lort) -> Stalfos
![Llort (Lort) CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/e/e5/Llort.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/b/b6/LA_Stalfos_Sprite.png" alt="Stalfos DMG" width="32" height="32"/>

# Enemy References (DMG Adventure II)

## Bago-Bago -> Piranha
![Bago-Bago CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/2/25/ZA_Bago-Bago.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/7/7a/LA_Piranha_Sprite.png" alt="Piranha DMG" width="32" height="32"/>

## Peahat -> Peahat
![Peahat CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/d/d1/ZA_Peahat_Sprite.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/c/c4/LA_Peahat_Sprite.png" alt="Peahat DMG" width="32" height="32"/>

## Tektite -> Tektite
![Tektite CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/3/32/ZA_Tektite_2.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/8/85/LA_Tektite_Sprite.png" alt="Tektite DMG" width="32" height="32"/>

## Deeler -> Beetle
![Deeler CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/5/51/ZA_Deeler_2.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/3/35/LA_Beetle_Sprite.png" alt="Beetle DMG" width="32" height="32"/>

## Molluska -> Spiny Beetle
![Molluska CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/c/cd/Krang.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/1/12/LA_Spiny_Beetle_Sprite.png" alt="Spiny Beetle DMG" width="32" height="32"/>

## Jackaroo -> Iron Mask
![Jackaroo CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/8/89/Dinosaur.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/9/95/LA_Iron_Mask_Sprite.png" alt="Iron Mask DMG" width="32" height="32"/>

## Vire -> Vire
![Vire CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/b/b5/ZA_Vire_Sprite.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/3/30/LA_Vire_Sprite.png" alt="Vire DMG" width="40" height="25"/>

## Pols Voice -> Pols Voice
![Pols Voice CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/9/9f/ZA_Pol%27s_Voice.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/a/ab/LA_Pols_Voice_Sprite.png" alt="Pols Voice DMG" width="32" height="32"/>

## Patra -> Oracle of Ages Eyesoar
![Patra CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/0/03/ZA_Patra_Sprite.png)
->
<img src="https://static.wikia.nocookie.net/zelda/images/6/65/Eyesoar.gif" alt="OOA Eyesoar DMG" width="32" height="32"/>

## Romraven -> Dacto
![Romraven CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/3/3d/Romraven.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/9/98/LA_Dacto_Sprite.png" alt="Dacto DMG" width="32" height="32"/>

## Lowder -> Hard Hat Beetle
![Lowder CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/2/29/ZA_Lowder.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/6/69/LA_Hardhat_Beetle_Sprite.png" alt="Hard Hat Beetle DMG" width="32" height="32"/>

## Vapora -> Oracle of Ages Smog
![Vapora CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/f/f8/Vapora.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/4/4f/OoA_Smog_Sprite.png" alt="OOA Smog DMG" width="48" height="48"/>

## Dragonfly -> Battle Bat (Grim Creeper's minion)
![Dragonfly CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/2/22/Dragonflies.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/0/0f/LA_Battle_Bat_Sprite.png" alt="Battle Bat DMG" width="32" height="32"/>

## Loccasins -> Battle Bat (Grim Creeper's minion)
![Loccasins CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/0/08/Loccasins.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/0/0f/LA_Battle_Bat_Sprite.png" alt="Battle Bat DMG" width="32" height="32"/>

## Volta -> Pairodd
![Volta CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/0/05/ZA_Volta_Sprite.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/0/02/LA_Pairodd_Sprite.png" alt="Pairodd DMG" width="32" height="32"/>

## Crystal Shard -> Oracle of Seasons Frypolar (ice attack)
![Crystal Shard CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/9/93/Crystal_Shards.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/c/c5/Frypolar_Ice.png" alt="OOS Frypolar DMG" width="32" height="32"/>

## Tornado -> Oracle of Ages/Seasons Gale seed
![Tornado CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/7/7d/ZA_Tornado_Sprite.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/c/c7/OoS_Gale_Seed_Sprite.png" alt="OOA/OOS Gale Seed DMG" width="32" height="32"/>

## Puffers (Baboon Head) -> Oracle of Seasons (modified) Magnite
![Puffers (Baboon Head) CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/1/1b/No_Clue.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/f/f5/OoS_Magunesu_North_Sprite.png" alt="OOS Magnite DMG" width="32" height="32"/>
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/7/7a/OoS_Magunesu_South_Sprite.png" alt="OOS OOS Magnite DMG" width="32" height="32"/>

## Gibdo -> Gibdo
![Gibdo CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/3/3e/ZA_Gibdo.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/0/0c/LA_Gibdo_Sprite.png" alt="Gibdo DMG" width="32" height="32"/>

# NPC References (DMG Adventure I)
Ogbam forest shop keeper -> Shopkeeper \
Witch in Ogbam forest -> Syrup \
Empty bottle lady -> Grandma Ulrira \
Hungry mother near Moblin inn -> Mamasha \
\
Moblin innkeep -> trendy game guy \
Moblin inn patron -> Madam Meow-meow, Grandpa Ulrira, Birdkeeper 

# NPC References (DMG Adventure II)
## Great Wimbich
Alice -> Oracle of Ages (past) young lady \
Eric/Ian -> Mamasha's twins \
Twin's Father -> Papahl \
Yvonne (music lover) -> Marin \
Ghost farmer -> Ghost \
Town square merchant -> Crazy Tracy \
Bored guy on Upper Street -> Oracle of Ages (past) young guy \
Dog on Upper Street -> Oracle of Ages (present) Mamamu Yan's dog \
General shop (dog owner) -> Oracle of Ages (present) Mamamu Yan \
General shop jester -> Oracle of Ages (present) Comedian \
Madam Kriggle -> Oracle of Ages (present) old lady \
Blacksmith -> Oracle of Ages (past) old guy

## Plain of Donora
Plain of Donora trader -> Oracle of Ages (present) Dr. Troy \
Plain of Donora gate keeper -> Oracle of Ages (present) young guy 

## Torian Forest
White Steed Lodgekeep -> Richard \
White Steed Patron -> Oracle of Ages (present) old guy \
White Steed Patron -> Oracle of Seasons drunk guy \
White Steed Barman -> Oracle of Seasons Mayor Ruul \
Waldensop -> Oracle of Ages (present) Mayor Plen \
Sir Basil -> Oracle of Ages (past) Guard 

## Verna
Gwynla (noise spell) -> Oracle of Ages (present) young lady \
Lonlyn (noise spell) -> Oracle of Seasons old guy \
Guy with Bard -> Oracle of Ages (past) young guy alt \
Bard -> Oracle of Seasons Guitar player 

## Around the Air Shrine
Bitterbeck (by the fire) -> Fisherman \
Nimonee (north of Air Shrine) -> Oracle of Seasons Impa \
Thabul (outside cave) -> Oracle of Seasons Old Lady
