# MathfinderBot

Mathfinder is a Discord bot built as a stat-tracker for Pathfinder 1e. Its features include:

- A math engine you can use to create useful expressions for your character, used together with a
- Statblock that keeps track of values and any bonuses applied to them, as well as determining how each bonus stacks.
- Character sheet imports from other software (PCGen, Pathbuilder, HeroLabs).
- Apply spells, effects, conditions to your character and your party (using mentions).
- Preset expressions for things like weapons and creature shapes, some of which can be customized before calling.
- Ability to turn formulae into buttons which you can call in rows and grids for easy access.
- Basic inventory management.
- Tools for DMs, including the ability to evaluate character sheets, secrets rolls, initiative tracking.
- Making your Pathfinder experience more convoluted than ever!

There are many help options built into the bot using the `/mf-help` command. These include examples on how to use particular commands. I will do my best to update both the documents located here and on the bot.

This bot is a big work in progress! Please be gentle. 


## Stats & Expressions
Statblocks contain two primary values: Stats and Expressions. 

Each `Stat` contains a base value, as well as a list of bonuses. Each `Bonus` contains a value, a name, and a bonus-type. Together, these are used to accurately calculate the total of any stat when one or many bonuses are applied. (Stacking rules are based on PF1e).

`Expressions` are formulae. These can represent anything from a constant number to an expression of expressions including any number of stats. 

For usability, stats and expressions share a pool of variable names.

*NOTE* — The Pathfinder default character sheet contains a number of both stats and expressions that represent the values you would find on any standard character sheet. Other than class-specific features, you should find the majority of what you need; the goal is minimal setup, while offering the freedom for anyone to customize it how they choose. You can view these values using the `/var` List options.

stats. simple enough.

![stats1](https://user-images.githubusercontent.com/10622391/192097536-4b77e851-29f9-4a46-8336-e846e4ea142f.jpg)

expressions. dont worry about it—unless you want to.

![expr](https://user-images.githubusercontent.com/10622391/192116307-e73c3cd1-1c4b-4b7e-9ad7-fd051ce01e1c.jpg)


## Rows & Grids
You can `/eval` stats and expressions individually, but the idea is to use Discords UI features as an interface to your sheet. This is where `Expression Rows` come into play.

These `Rows` are sets of buttons. These can call any value from your sheet or be entirely unique. This is useful when representing something like a weapon's attack and damage values. You can create your own rows from scratch using `/var Set-Row`, or they can be saved from a preset (look up /preset-weapon for more info). use the `/row` command to call any created rows.

`Grids` are sets of expression rows. Up to 5 rows can be called in this manner per command, creating an (up to) 5x5 grid of buttons. Use `/var Set-Grid` to create a grid using expression row names. Use `/grid` to call any created grids.

a row

![onerow](https://user-images.githubusercontent.com/10622391/192144466-0847fa71-1a0a-4820-8700-91190e345365.jpg)

a grid (a set of rows)

![grid](https://user-images.githubusercontent.com/10622391/192144484-d20f109e-19d9-4562-8a28-d1795dbd3531.jpg)

my acrobatics isn't good. nice roll though!

![button](https://user-images.githubusercontent.com/10622391/192144530-b4805f75-6ac6-4db2-a477-7a615342878e.jpg)

## Character Sheet Imports
While you can setup a character by manually setting each value, this is not ideal. Mathfinder currently supports three different options for character imports, so that you can update your character at each level.

### PCGen
 - Using the export option `csheet_fantasy_rpgwebprofiler.xml`. Tested with v6.09.05.

### HeroLabs
 - Using the XML export option

### Pathbuilder
 - Using the exported PDF


These files can be uploaded to update any created character. There are specific limitation when parsing some sheets. For instance, not all bonus-types may be known for a given stat, and cannot be applied accurately, but the totals should remain correct. This can affect the proper calculation of stacking bonuses. I do my best!


## Command Reference
There are other commands than the ones listed below. I've only documented the ones I feel are worth using/testing at the moment. Almost all variable names are upper-case and underscore-spaced (like `SHORT_SWORD` or `STR_SCORE`). However, when using them, they are not case-sensitive, and you can use spaces or underscores to separate words (`short sword` should work in place of `SHORT_SWORD`).

There are also `dm` versions of some commands, which add an additional `target` option for selecting other player's active sheets. These require the `DM` role.




### **-CHARACTER-**

usage: /char `mode` `char-name` `game`

-:-

![char](https://user-images.githubusercontent.com/10622391/192044180-e25c1784-b76b-40a7-be83-5a4ec68fc2e4.jpg)


`mode`

 - —`Set` Set an active character.
   
   - `char-name` The name of the character to set.

 - —`New` Create a new character. This is a required step before importing any character sheet from any third-party app.
   
   - `char-name` The name of the character to create.
   - `game` *optional & not recommended.* The selected game to use. The default is Pathfinder. Any other option is purely experimental.

 - —`List` This will list any created characters you have.

 - —`Export` *EXPERIMENTAL.* This will export any active character into JSON format.

 - —`Delete` Delete a character.
   - `char-name` The name of the character to delete. This will prompt you for confirmation.




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



### **-EVALUATE-**

usage: /eval `expr`

-:-

`expr`

 - The expression to evaluate.

cool?

![eval0](https://user-images.githubusercontent.com/10622391/192032624-f0e56353-731d-4b15-9827-606ee703b1a8.jpg)

more practical

![eval1](https://user-images.githubusercontent.com/10622391/192047953-34581fa4-bf82-4986-93d7-20138f92f437.jpg)

wtf

![eval2](https://user-images.githubusercontent.com/10622391/192032806-774d28bd-acf2-4908-b413-3dcfa75fe8ec.jpg)

cmon

![wtf](https://user-images.githubusercontent.com/10622391/192057007-8601126b-b0b0-489b-bcb1-7fd81ced099b.jpg)



#### Remarks
`/eval` supports many different math operators: `+` `-` `*` `/` `>` `<` `==` `!=` `<=` `>=` `%` `()` `=` `+=` `-=` `*=` `/=` `&&` `||` `?:`. Use `/mf-help` on the bot for more examples.

Dice expressions are also supported within any formula. `1d20` is a valid expression. You can also use rerolls and multipliers. `3d6r1` would "roll" 3 six-sided die, rerolling any dice that come up 1 (the initial roll only). `(3d6*2)` would effectively turn into `6d6`.

Assignment operators (`=`, `+=`, etc) can be used to change the current **base** value of any Stat. The `@` prefix (ex. `@STR_SCORE`) will let you view or utilize the base value of any stat (no bonuses applied).

![bonus](https://user-images.githubusercontent.com/10622391/192063905-989523bc-14ef-4d21-b185-c0e1d84ee1f4.jpg)

To modify bonus values instead, you can use the special `$` operator. Adding a specific bonus to any stat can be done as follows: `STATNAME +$ NAME:TYPE:VALUE`. A name and type are required for determining which bonuses stack. Types can be represented by numbers or names (7 and ENHANCEMENT are identical). To remove a bonus from a stat, you can do: `STATNAME -$ NAME`. This will effectively remove all bonuses with that name from the stat. You can view a specific bonus by doing: `STATNAME $ TYPE`. You can also use `/var List-Bonuses` to see all bonuses applied to all stats.

![types](https://user-images.githubusercontent.com/10622391/192049011-451e78d3-b0db-429c-a74b-75b5fa0f6817.jpg)

The `BASE` type is a special bonus that overrides all other values, including the original base value. This is useful for certain modifiers such as size mods or spells like *feeblemind*, where you need to set a score to a specific value regardless of its current value.

*NOTE* — `/eval` returns integer values only. This comes with some limitations in how evaluations are performed. For example, true and false are represented by 1 and 0 respectively. `TRUE`/`FALSE` are hardcoded variables that can be used for readability. This also applies to all bonus types and their respective numbers.



### **-INVENTORY-**

usage: /inv `action` `item` `qty` `attachment`

-:-

![inv](https://user-images.githubusercontent.com/10622391/192052270-6623db24-1040-4316-a250-fcfa20adec87.jpg)

`action`

- —`Add` Add one or many items to your active character's inventory. Leave all other fields blank to bring up a window where you can input a list of items.
  - `item` *optional* The syntax for adding an item is `NAME:WEIGHT:VALUE`. For example, `Sword:5:10` would add a Sword of 5 weight and a value of 10. Only name is required.
  - `qty` *optional.* How many to add. Default is 1.

- —`Import` Import a list of items. CAUTION—This will **REPLACE** any existing list. If you want to add many items, use the `Add` action. You can copy/paste your text file into the subsequent modal.
  - `attachment` A text file containing one item per line.

- —`Export` Export the current list to a text file.

- —`Remove` Remove an item from your list.
  - `item` The name or index number of the item. If a name is given, it will remove the first occurence any matched value.
  - `qty` The number of the specified items to remove.

- —`List` List your current inventory.



### **-MODIFIER-**

usage: /mod `action` `mod-name` `target`

-:-

`action`

 - —`Add` Add the following mod-name.
 - —`Remove` Remove the following mod-name.

`mod-name` Name of the modifier (use /var List-Mods for a coomprehensive list).

`target` *optional.* Target or targets using @mentions. Leave blank to target yourself.

![mod0](https://user-images.githubusercontent.com/10622391/192043634-72ca55d6-5a9d-4936-8356-7eedff008113.jpg)

![mod1](https://user-images.githubusercontent.com/10622391/192043649-46aa7dcc-0f48-4c53-b1a5-5d4198febdc4.jpg)


#### Remarks
This command will add or remove a modifier to your current character. Some modifiers contain sub-options, such as `BEAST_SHAPE` or any spell that scales with caster level. These options generally appear as buttons.



### **-VAR-**

usage: /var `action` `var-name` `value`

-:-

`action`

 - —`Set-Expression` 
   - `var-name` Name of the expression.
   - `value` Expression to create. 

 - —`Set-Row` 
   - `var-name` Row name. This will bring up a modal window, where you can make up to 5 expressions. The syntax is `LABEL:EXPRESSION`. The label is optional—if omitted it will use the expression as the label.

 - —`Set-Grid`
   - `var-name` Grid name. The same as Set-Row except you can specify rows instead of expressions.

 - —`Set-Craft` *EXPERIMENTAL.* This lets you set a mundane item to craft. 
   - `var-name` Item name. 
   - `value` DC to craft.

 - —`List-Stats` Lists all stats for an active character.

 - —`List-Expressions` Lists all expressions for an active character.

 - —`List-Bonus` Lists all bonuses applied to stats.

 - —`List-Row` Lists all saved Rows. 
   - `var-name` *optional.* List a single Row's expressions.

 - —`List-Presets` Lists all weapon presets.

 - —`List-Shapes` Lists all available creature shapes.

 - —`List-Grids` Lists all saved Grids.

 - —`List-Crafts` List all active crafts.

 - —`Remove-Variable` Removes a Stat, Expression, Row, or Grid. 
   - `var-name` The variable name to remove.


### **-PRESET-ARMOR-**

usage: /preset-armor `number-or-name` `enhancement`

-:-

`number-or-name`
 - The name or index number associated with it (use /var List-Armor to see a comprehensive list).

`enhancement` *optional*
 - The enhancement bonus (if any) to AC.

![hara](https://user-images.githubusercontent.com/10622391/192118521-60e4c411-a50b-49dd-8793-9ffb6e9bf74d.jpg)

#### Remarks
This command will apply the stats gained from a specific set of armor (or a shield) to an active character. For shields, this applies a shield bonus to AC and skill check penalties. For armor, this applies an armor bonus to AC, skill check penalties, and max AC gained from Dexterity. It will attempt to remove and previous armor or shield bonuses depending.


### **-PRESET-WEAPON-**

usage: /preset-weapon `number-or-name` `hit-mod` `damage-mod` `hit-bonus` `dmg-bonus` `size`

-:-

`number-or-name`
 - The name or index number associated with it (use /var List-Weapons to see a comprehensive list).

`hit-mod`
 - The modifier used for hitting.

`damage-mod` *optional*
 - The modifier used for damage

`hit-bonus` *optional*
 - The bonus to hit

`dmg-bonus` *optional*
 - The bonus damage

`size` *optional*
 - The size of the character. If left blank, it will check the character's Stackblock for size. If none is found, it will default to medium.


![preset](https://user-images.githubusercontent.com/10622391/192030455-2149b615-ea3f-4663-b55d-5d8a56846b8f.jpg)

![weapon](https://user-images.githubusercontent.com/10622391/192163817-021abd3f-c883-40d6-a021-751cd17c653e.jpg)

![preset-2](https://user-images.githubusercontent.com/10622391/192030805-9971520e-2886-4b47-b7f0-38eb652e402e.jpg)


#### Remarks
You can use `/preset-save` with a `name` to save the last generated preset to your active character sheet. You can then call it with /row.




### **-SHAPE-**

usage: /shape `number-or-name` `hit-mod` `multi-attack`

-:-

`numer-or-name`
 - The name or index number associated with it (use /var List-Shapes to see a comprehensive list).
 
`hit-mod`
 - The modifier used for hitting.

`multi-attack` *optional.* Set to true if you possess the `Multiattack` feat. This will adjust the penalty on your secondary attack.
 
#### Remarks
`/shape` is meant to be used in-tandem with a polymorph `/mod`, such as `BEAST_SHAPE`. This will generate the attacks (primary and/or secondary) and natural weapons associated with a particular creature's shape. In addition, it will list any speeds, senses, or special abilities you may receive from taking the creature's shape. Be sure to follow the particular spell's allowances, as many creatures are listed with their maximum possible features.

![shape](https://user-images.githubusercontent.com/10622391/192065898-00161ce4-7775-4b49-b7bf-34c11d8631d3.jpg)

