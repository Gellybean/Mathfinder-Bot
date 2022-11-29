# MathfinderBot v0.4

Mathfinder is a Discord bot built as an expression parser and stat-tracker for Pathfinder 1e. Its features include:

- A math engine you can use to create useful expressions for your character
- Fully customizable statblock that holds all of your variables
- Import from other programs to update your stats
- Apply spell effects, conditions, class abilities
- Transform expressions into buttons
- Modifiable presets for weapons, armor, beast shapes, and more
- Spell reference with options for calculating values that rely upon caster level
- Basic inventory management with a large list of built-in items
- Tools for DMs, including the ability to evaluate character sheets, secret rolls, initiative tracking, roll requests
- Bestiary containing complete entries and buttons for melee/ranged attacks
- Making your Pathfinder experience more convoluted than ever!

This bot contains a number of commands, but its core premise revolves around one: [`/eval`](https://github.com/Gellybean/Mathfinder-Bot/wiki/eval). This is where you can roll dice, create and save expressions, as well as modify your statistics using pathfinder's bonus-stacking rules. Most other commands utilize eval in one way or another.

![roll](https://user-images.githubusercontent.com/10622391/204659521-9ca808e2-21b1-42f3-8c88-b2b5d8bc04cb.jpg)
![skull](https://user-images.githubusercontent.com/10622391/204660424-ceda70b3-94fe-44d4-85df-6c490bcba98c.jpg)
![fire1](https://user-images.githubusercontent.com/10622391/204660444-57e9e957-22b6-4af6-8e54-f9947914c400.jpg)


 - [Bot Invite.](https://discord.com/api/oauth2/authorize?client_id=1003844628841238588&permissions=277025712192&scope=bot%20applications.commands)
 - [Discord Server.](https://discord.gg/z2rVRnVjb7)

This is a big work in progress. I'm sure there are plenty of bugs to work out, and many improvements to make. Please feel free to let me know on here or Discord. The [**Command Reference**](https://github.com/Gellybean/Mathfinder-Bot/wiki) should help you with basic usage.

## Getting Started
**NOTE**—You don't need to create a character to utilize most commands. The first time you use [`/eval`](https://github.com/Gellybean/Mathfinder-Bot/wiki/eval), it will generate a blank sheet for you. 

To create a character, use the [`/char`](https://github.com/Gellybean/Mathfinder-Bot/wiki/char) command with the `New` action.

Once you character is created, you can update it using the `Update` action, as well as list your stats and expressions using [`/var`](https://github.com/Gellybean/Mathfinder-Bot/wiki/var)

new char

![newchar1](https://user-images.githubusercontent.com/10622391/203803673-7a631c0e-6572-4a9a-9653-61ca9e493ae8.jpg)
 
update

![update](https://user-images.githubusercontent.com/10622391/196033832-3c30f5bd-4573-45bc-bd8e-e20d92b5de2d.jpg)


## Stats & Expressions
Statblocks contain three primary values: Stats, Expressions, and Expression Rows (buttons). 

Each `Stat` contains a base value, as well as a list of bonuses. Each `Bonus` contains a value, a name, and a bonus-type. Together, these are used to accurately calculate the total of any stat when one or many bonuses are applied. (Stacking rules are based on PF1e).

`Expressions` are formulae. These can represent anything from a constant number to an expression of expressions including any number of stats. 

For usability, stats and expressions share a pool of variable names.

`Expression Rows` are groups of buttons that execute an expression. You can assign them to a variable using /var with the `Set-Expression` action. You can then call them at any time using `/row`.

**NOTE** — The default character sheet contains a number of both stats and expressions that represent the values you would find on any standard character sheet. This includes ability scores, saves, skills, cmb/cmd, modifiers, etc. Many of these values are important when using certain features, such as preset modifiers, that affect specific variables.

To view these values, use `/var` with the `List-Vars` option.

stats

![stats1](https://user-images.githubusercontent.com/10622391/192097536-4b77e851-29f9-4a46-8336-e846e4ea142f.jpg)

expressions

![expr](https://user-images.githubusercontent.com/10622391/192116307-e73c3cd1-1c4b-4b7e-9ad7-fd051ce01e1c.jpg)


## Rows
You can `/eval` expressions individually, or you can use Discord's UI features. `/row` is used for this.

![expr](https://user-images.githubusercontent.com/10622391/193103316-36802b25-9370-4375-b8ff-3821b18ba8f9.jpg)

These rows are sets of buttons. These can call any value from your sheet or be entirely unique. This is useful when representing something like a weapon's attack and damage values. You can create your own rows from scratch using `/var` with the `Set-Row` action, or they can be saved from a preset (such as weapons in /item). use the `/row` command to call any created rows.


a row

![onerow](https://user-images.githubusercontent.com/10622391/192144466-0847fa71-1a0a-4820-8700-91190e345365.jpg)

another row

![grid](https://user-images.githubusercontent.com/10622391/192144484-d20f109e-19d9-4562-8a28-d1795dbd3531.jpg)

my acrobatics isn't good. nice roll though!

![button](https://user-images.githubusercontent.com/10622391/192144530-b4805f75-6ac6-4db2-a477-7a615342878e.jpg)

## Presets

![addu](https://user-images.githubusercontent.com/10622391/195965764-abe40bac-f9ce-47b1-80bd-c11d8c124f0a.jpg)
![dire](https://user-images.githubusercontent.com/10622391/195958967-1de2c996-f65d-47c3-8119-832e9a71b463.jpg)

MF-Bot comes with many different preset commands for things like equipment, creatures, stat modifiers including spells and conditions. You can bring up pre-programmed attacks for creatures, or use your own stats when selecting different creature shapes. Check out the Wiki entries for more details.

 - [/best](https://github.com/Gellybean/Mathfinder-Bot/wiki/best#bestiary) — Bestiary
 - [/item](https://github.com/Gellybean/Mathfinder-Bot/wiki/item#item) — View or Add items to your inventory, generate preset expressions for weapons, apply bonuses from equipment with a button click.
 - [/rule](https://github.com/Gellybean/Mathfinder-Bot/wiki/rule#rule) — List common rules, conditions, class abilities.
 - [/shape](https://github.com/Gellybean/Mathfinder-Bot/wiki/shape#shape) — List abilities and generate expressions for your attacks.
 - [/spell](https://github.com/Gellybean/Mathfinder-Bot/wiki/spell#spell) — List spells, provide an optional caster level for scaling values.



## Character Sheet Imports
While you can setup a character by manually modifying values, why not use your favorite character creator instead? 

Mathfinder currently supports a few options for character imports. This will override any pertinent values, so anytime your stats would change, you can easily update your sheet. This way you can use apps more suited for character management while keeping your expressions up to date.

### PCGen
 - Using the export option `csheet_fantasy_rpgwebprofiler.xml`. Tested with v6.09.05.

### HeroLabs
 - Using the XML export option

### Pathbuilder
 - Using the exported PDF

### Mottokrosh's Character Sheet
 - Using the JSON export
 
 ### RPG Scribe
 - Using the exported TXT file.

**NOTE** — There are specific limitation when parsing different sheets. For instance, not all bonus types may be known for a given stat, and cannot be applied accurately, but the totals should remain correct. This can affect the proper calculation of stacking bonuses. I do my best! Also, expect general issues with parsing—Some options I've tested more thoroughly than others. Please let me know, and I will fix them.


## Q&A

### -> Does it support things beyond basic actions? (like attack type feats? Vital strike?)
*from /u/Elgatee*

![expr3](https://user-images.githubusercontent.com/10622391/194180919-4701f99f-0d71-44ff-a7b2-fb9bbd4da515.jpg)

For Vital Strike, you would need to multiply the weapon's damage dice (for example, 3d6) like this: `(3d6*2)`. This works just **fine**, but you could get a little fancier and create a variable that holds the multiplier, for example, `VS`. You could then do `(3d6*VS)`. If you were to ever get Improved VS, you could change the single value `VS` from 2 to 3. If you only have a single weapon relying on Vital Strike, this is probably overkill.

For something like *Power Attack*, however, creating a variable is more useful since it relies upon a value that scales with your level.

 - Power Attack - hit: `1 + BAB/4`
 - Power Attack - damage : `2 + (BAB/4 * 2)`

Since receiving this question, I've added default expressions representing both: `PA_ATK` and `PA_DMG`.

Most people are probably going to use Power Attack two-handed. This is where [functions](https://github.com/Gellybean/Mathfinder-Bot/wiki/eval#functions) come in handy.
 - Power Attack (two-handed) damage: `th(PA_DMG)`
 - Power Attack (off-handed) damage: `oh(PA_DMG)`

Finally, we can combine it with an:
 - attack roll: `PA_ATK + ATK_STR`. We can call this `PWR_HIT`
 - damage roll: `DMG_STR + th(PA_DMG)`. Let's call this one `PWR_DMG`

The attack and damage rolls would be modifiers for any attack you'd wish to use it with. For example, you would add +1 to the attack roll with a masterwork weapon. For damage, of course, add your weapons dice and any additional modifiers: `2d6 + PWR_DMG`. I would suggest putting weapon expressions into a `/row` instead of directly into your character sheet. You can do this by using `/var` and `Set-Row`.

![gs](https://user-images.githubusercontent.com/10622391/196036502-2453a10c-383e-46e1-a94e-04910adc2712.jpg)

![row](https://user-images.githubusercontent.com/10622391/196036387-ca0fbaa2-c09f-41a0-a295-36783f241b3b.jpg)



### -> Does it support getting X to Y?
*from /u/Elgatee*

A common example would be changing your Intimidate skill to use Strength instead of Charisma via [Intimidating Prowess.](https://aonprd.com/FeatDisplay.aspx?ItemName=Intimidating%20Prowess)

The default expression for Intimidate (`ITM`) is: `1d20 + CHA + SK_ALL + SK_ITM`.

You can use [`/var`](https://github.com/Gellybean/Mathfinder-Bot/wiki/var#var) with the `Set-Expression` action and `ITM` as the var-name. This will bring up a window with the original expression. Just change CHA to STR:

![setexpr](https://user-images.githubusercontent.com/10622391/194178322-48c6c21a-508c-4107-ac1e-77a7d9f7f537.jpg)

![setexpr1](https://user-images.githubusercontent.com/10622391/194178818-b3c40311-35d6-48f3-8064-bd58b6ab8666.jpg)
![setexpr2](https://user-images.githubusercontent.com/10622391/194178823-343919f1-2cde-4bbb-af74-8a76b4cd6688.jpg)


### -> Does it support custom skills?
*from /u/Elgatee* (great questions all around)

Yep. While there are a number of ways to accomplish this, I will use the methods I use in the default statblock.

First, create a new `Stat` using [`/eval`](https://github.com/Gellybean/Mathfinder-Bot/wiki/eval) to assign a new variable.

![sk](https://user-images.githubusercontent.com/10622391/194179766-0bdd32dd-7cb7-4261-aa3b-4e6f9fd402a0.jpg)

Then, create a new `Expression` using `/var` `Set-Expression` with a given var-name (I use just the three-letter abbreviation for all my expressions. It is often better to keep your expression names short because they are called directly more often). You can use the X to Y example above as a blueprint for how your skill may be calculated. 

*NOTE* — `SK_ALL` is a variable created for convenience purposes, mainly for modifiers that affect all skills. It is not required, but if removed it will cause problems with certain features, like preset-mods and certain character imports. I would recommend keeping it in all custom skill formulae unless you have a specific reason not to.

