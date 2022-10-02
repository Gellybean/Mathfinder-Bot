# MathfinderBot

Mathfinder is a Discord bot built as a stat-tracker for Pathfinder 1e. Its features include:

- A math engine you can use to create useful expressions for your character, used together with a
- Fully customizable statblock that holds all of your variables
- Character sheet imports from other programs (PCGen, Pathbuilder, HeroLabs)
- Apply spells, effects, conditions to your character and your party (using mentions)
- Turn expressions into buttons which you can call in rows and grids for easy access
- Modifiable presets for weapons, armor, and creature shapes
- Spell reference with options for calculating DCs.
- Basic inventory management
- Tools for DMs, including the ability to evaluate character sheets, secrets rolls, initiative tracking
- Making your Pathfinder experience more convoluted than ever!


While there are a number of features included with this bot, the main purpose is to make tallying stats (particularly in combat) easier. When it comes to the typical 1s and 2s that Pathfinder is known for, it can be a little confusing—not only because of the number of modifiers, but their bonus types as well. The aim is to make the application and calculation of these modifiers as quick and accurate as possible.

To help further with this, anyone with the `DM` role can do evaluations on their player's statblocks. As well, **anyone** can apply and remove preset modifiers to themselves and others. This means, for example, a Bard can apply his inspiration bonuses to his party with a command, or any cool Wizard can drop his most useful spell on the party... It's Haste—obviously.

[Bot Invite.](https://discord.com/api/oauth2/authorize?client_id=1003844628841238588&permissions=277025712192&scope=bot%20applications.commands)

[Give it a try on the MF Discord.](https://discord.gg/z2rVRnVjb7)

This is a big work in progress! I'm sure there are plenty of bugs to work out, and many improvements to make. 

## Getting Started
To create a character, use the `/char` command with the `New` option. Select a name in the `char-name-or-number` field.

Once you character is created, you can update it with an exported character sheet from a number from different programs, as well as any saved characters from Mathfinder. You can do this by using the `/char-update` command. See the /char reference below for more details.

## Stats & Expressions
Statblocks contain two primary values: Stats and Expressions. 

Each `Stat` contains a base value, as well as a list of bonuses. Each `Bonus` contains a value, a name, and a bonus-type. Together, these are used to accurately calculate the total of any stat when one or many bonuses are applied. (Stacking rules are based on PF1e).

`Expressions` are formulae. These can represent anything from a constant number to an expression of expressions including any number of stats. 

For usability, stats and expressions share a pool of variable names.

*NOTE* — The default character sheet contains a number of both stats and expressions that represent the values you would find on any standard character sheet. This includes ability scores, saves, skills, cmb/cmd, modifiers, etc. Other than class-specific features, you should find most of what you need; the goal is minimal setup with the freedom to customize how you want. To view these values, use `/var` with the `List-Vars` option.

stats

![stats1](https://user-images.githubusercontent.com/10622391/192097536-4b77e851-29f9-4a46-8336-e846e4ea142f.jpg)

expressions

![expr](https://user-images.githubusercontent.com/10622391/192116307-e73c3cd1-1c4b-4b7e-9ad7-fd051ce01e1c.jpg)


## Rows & Grids
You can `/eval` expressions individually, but the idea is to use Discords UI features for any frequently used actions. `Expression Rows` are used for this.

![expr](https://user-images.githubusercontent.com/10622391/193103316-36802b25-9370-4375-b8ff-3821b18ba8f9.jpg)

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

*NOTE* — There are specific limitation when parsing different sheets. For instance, not all bonus types may be known for a given stat, and cannot be applied accurately, but the totals should remain correct. This can affect the proper calculation of stacking bonuses. I do my best!


## Command Reference
Almost all variable names are SCREAMING_SNAKE_CASE (like `SHORT_SWORD` or `STR_SCORE`). However, when calling them, they are not case-sensitive (`short_sword` will work in place of `SHORT_SWORD`). When using options like preset commands or calling a row, you can use spaces in place of underscores. hiss.

- [/char](https://github.com/Gellybean/Mathfinder-Bot/blob/main/char.md) 
- [/eval](https://github.com/Gellybean/Mathfinder-Bot/blob/main/eval.md) 
- [/inv](https://github.com/Gellybean/Mathfinder-Bot/blob/main/inv.md)
- [/preset-x](https://github.com/Gellybean/Mathfinder-Bot/blob/main/presets.md)
- [/var](https://github.com/Gellybean/Mathfinder-Bot/blob/main/var.md)
- [/init](https://github.com/Gellybean/Mathfinder-Bot/blob/main/init.md)
- [/req](https://github.com/Gellybean/Mathfinder-Bot/blob/main/req.md)

