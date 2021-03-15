# DMG Adventure II
A continuation of https://github.com/john-lay/dmg-adventure built with GB Studio 2-beta4

# Technical notes

## Variable list

A listing of variables and their types in re-usable components (Actors/Scenes)

### Global
* `$00$: Variable 000` Health - `number`. (0-4 Indicates the number of hearts Zelda has)
* `$01$: Variable 001` Rupees - `number`. (Indicates the number of rupees Zelda has collected)
* `$02$: Variable 002` Collectable - `byte`.
  * (Flag 1 represents the enemy dropping a rupee)
  * (Flag 2 represents the enemy dropping a heart)
  * (Flag 3 is the Noise spell)
  * (Flag 4 is the Harp)
  * (Flag 5 is feather)
  * (Flag 6 is flute)
  * (Flag 7 is pyros)
  * (Flag 8 is broadsword)
* `$03$: Variable 003` Equipped - `byte`.
  * (Flag 1 represents Zelda has the wand equipped)
  * (Flag 2 represents Zelda has the Noise spell equipped)
  * (Flag 3 represents Zelda has the Turquoise Ring spell equipped)
  * (Flag 4 represents Zelda has the Jade Amulet spell equipped)
  * (Flag 5 represents Zelda has the feather spell equipped)
  * (Flag 6 represents Zelda has the pyros spell equipped)
  * (Flag 7 represents Zelda has the broadsword equipped)
  * (Flag 8 represents Zelda has the Rings of Fire equipped)
* `$04$: Variable 004` Purchasable - `byte`.
  * (Flag 1 is the Turquoise Ring)
  * (Flag 2 is the Jade Amulet)
  * (Flag 3 is the Rings of Fire)
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

# Enemy References
Where possible enemies have been identified in Zelda's Adventure and their conterpart has been used from Link's Awakening. When the enemy doesn't exist in Link's Awakening I've tried to carefully substitute it with an enemy that is both similar and likely to be unique to Link's Awakening. This is to prevent future iterations of the project from having collisions when I try to identify enemies later in the game and find I've already used their counterpart.
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
![Peahat CDi](https://static.wikia.nocookie.net/zelda_gamepedia_en/images/e/e5/Llort.png)
->
<img src="https://static.wikia.nocookie.net/zelda_gamepedia_en/images/b/b6/LA_Stalfos_Sprite.png" alt="Stalfos DMG" width="32" height="32"/>
