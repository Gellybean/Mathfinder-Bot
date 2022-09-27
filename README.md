# MathfinderBot

Mathfinder is a Discord bot built as a stat-tracker for Pathfinder 1e. Its features include:

- A math engine you can use to create useful expressions for your character, used together with a
- Statblock that keeps track of values and any bonuses applied to them, as well as determining how each bonus stacks.
- Character sheet imports from other software (PCGen, Pathbuilder, HeroLabs).
- Apply spells, effects, conditions to your character and your party (using mentions).
- Turn expressions into buttons which you can call in rows and grids for easy access.
- Presets expressions for things like weapons and creature shapes, some of which can be customized before calling.
- Basic inventory management.
- Spell reference.
- Tools for DMs, including the ability to evaluate character sheets, secrets rolls, initiative tracking.
- Making your Pathfinder experience more convoluted than ever!

There are many help options built into the bot using the `/mf-help` command. These include examples on how to use particular commands. I will do my best to update both the documents located here and on the bot.

This bot is a big work in progress! Please be gentle. 


## Stats & Expressions
Statblocks contain two primary values: Stats and Expressions. 

Each `Stat` contains a base value, as well as a list of bonuses. Each `Bonus` contains a value, a name, and a bonus-type. Together, these are used to accurately calculate the total of any stat when one or many bonuses are applied. (Stacking rules are based on PF1e).

`Expressions` are formulae. These can represent anything from a constant number to an expression of expressions including any number of stats. 

For usability, stats and expressions share a pool of variable names.

*NOTE* — The Pathfinder default character sheet contains a number of both stats and expressions that represent the values you would find on any standard character sheet. Other than class-specific features, you should find the majority of what you need; the goal is minimal setup, while offering the freedom for anyone to customize it how they choose. You can view these values with the List-Vars command using `/var`.

stats. simple enough.

![stats1](https://user-images.githubusercontent.com/10622391/192097536-4b77e851-29f9-4a46-8336-e846e4ea142f.jpg)

expressions. dont worry about too much about it—unless you want to.

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
While you can setup a character by manually modifying each value, this is not ideal. Mathfinder currently supports a few options for character imports. This will override any pertinent values, so anytime your stats would change (level up, new stat-changing item), you can easily update your sheet.

### PCGen
 - Using the export option `csheet_fantasy_rpgwebprofiler.xml`. Tested with v6.09.05.

### HeroLabs
 - Using the XML export option

### Pathbuilder
 - Using the exported PDF

*NOTE* — There are specific limitation when parsing different sheets. For instance, not all bonus-types may be known for a given stat, and cannot be applied accurately, but the totals should remain correct. This can affect the proper calculation of stacking bonuses. I do my best!


## Command Reference
There are other commands than the ones listed below. I've only documented the ones I feel are worth using/testing at the moment. Almost all variable names are SCREAMING_SNAKE_CASE (like `SHORT_SWORD` or `STR_SCORE`). However, when calling them, they are not case-sensitive, and you can use spaces or underscores to separate words (`short sword` will work in place of `SHORT_SWORD` during an /eval). HISS.

There are also `dm` versions of some commands, which add an additional `target` option for selecting other player's active sheets. These require the `DM` role.

char.md

