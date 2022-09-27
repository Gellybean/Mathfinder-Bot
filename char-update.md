### **-CHARACTER-UPDATE-**

usage: /char-update `sheet-type` `file`

-:-

`sheet-type`

 - —`Pathbuilder` Pathbuilder PDF export.
   - Pathbuilder's PDF export is actually a fillable PDF. This allows you to easily change the values before dropping it in. The parser will attempt to automatically create expression rows (buttons) for your attacks, which means you can create the expressions you want in the attack and damage fields. You can then call the attack(s) using /row with the given name. *Note* — When typing in these fields, some symbols may look incorrect. This is just a visual bug. 

this will create a row with a button that represents `1d20+ATK_DEX` for hit (there is actually an underscore there, not spaces), and `1d10` for damage. crit is also supported now.

![tp](https://user-images.githubusercontent.com/10622391/192145947-61a74f62-fdb7-4182-be80-499e20d80f5b.jpg)

 - —`HeroLabs` HeroLabs XML export.

 - —`PCGen` Export using the `csheet_fantasy_rpgwebprofiler.xml` option.


`file`

 - The file to use.

![update](https://user-images.githubusercontent.com/10622391/192043907-a72d879d-9fed-42ce-a0df-050e60af9862.jpg)


#### Remarks
This feature is meant to update your character at each level (or whenever you feel like it) by importing a character sheet from a program more suited for character advancement. It should not remove any custom made stats, but it *will* override any defaults with ones from the sheet.
