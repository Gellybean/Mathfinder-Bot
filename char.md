## **CHARACTER**

usage: /char `mode` `char-name-or-number` `game`

-:-

![char](https://user-images.githubusercontent.com/10622391/192044180-e25c1784-b76b-40a7-be83-5a4ec68fc2e4.jpg)


`mode`

 - —`Set` Set an active character.
   
   - `char-name-or-number` The name or index number of the character to set.

 - —`New` Create a new character. This is a required step before importing any character sheet from any third-party app.
   
   - `char-name-or-number` The name of the character to create.
   - `game` *optional & not recommended.* The selected game to use. The default is Pathfinder. Any other option is purely experimental.

 - —`List` This will list any created characters you have.

 - —`Export` This will export any active character into JSON format.

 - —`Delete` Delete a character.
   - `char-name-or-number` The name or index number of the character to delete. This will prompt you for confirmation.


## **CHARACTER-UPDATE**

usage: /char-update `sheet-type` `file`

-:-

`sheet-type`

 - —`JSON` Mathfinder export.
   - Using this option will override the entire sheet, other than character name.

 - —`Pathbuilder` Pathbuilder PDF export.
   - Pathbuilder's PDF export is actually a fillable. This allows you to easily change the values before dropping it in. The parser will attempt to automatically create expression rows (buttons) for your attacks, which means you can create the expressions you want in the attack and damage fields. You can then call the attack(s) using /row with the given name. 

this will create a row with a button that represents `1d20+ATK_DEX` for hit (there is actually an underscore there, not spaces), and `1d10` for damage. crit is also supported now.

![tp](https://user-images.githubusercontent.com/10622391/192145947-61a74f62-fdb7-4182-be80-499e20d80f5b.jpg)

 *NOTE* — When typing in these fields, some letters may look incorrect. This is just a visual bug. 
 
 - —`HeroLabs` HeroLabs XML export.

 - —`PCGen` Export using the `csheet_fantasy_rpgwebprofiler.xml` option.
 
 - —`Mottokrosh` JSON export.


`file`

 - The file to use.

![update](https://user-images.githubusercontent.com/10622391/192043907-a72d879d-9fed-42ce-a0df-050e60af9862.jpg)


### Remarks
This feature is meant to update your character at each level (or whenever you feel like it) by importing a character sheet from a program more suited for character advancement. Other than the Mathfinder export, it should not remove or change any custom made stats.
