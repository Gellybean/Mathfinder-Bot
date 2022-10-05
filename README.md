# MathfinderBot

Mathfinder is a Discord bot built as a stat-tracker for Pathfinder 1e. Its features include:

- A math engine you can use to create useful expressions for your character, used together with a
- Fully customizable statblock that holds all of your variables
- Character sheet imports from other programs (PCGen, Pathbuilder, HeroLabs, Mottokrosh)
- Apply spells, effects, conditions to your character and your party (using mentions)
- Turn expressions into buttons which you can call in rows and grids for easy access
- Modifiable presets for weapons, armor, and creature shapes
- Spell reference with options for calculating DCs.
- Basic inventory management
- Tools for DMs, including the ability to evaluate character sheets, secrets rolls, initiative tracking
- Making your Pathfinder experience more convoluted than ever!


While there are a number of features included with this bot, the main purpose is to make tallying stats (particularly in combat) easier. When it comes to the typical 1s and 2s that Pathfinder is known for, it can be a little confusing—not only because of the number of modifiers, but their bonus types as well. The aim is to make the application and calculation of these modifiers as quick and accurate as possible.

To help further with this, anyone with the `DM` role can do evaluations on their player's statblocks. As well, **anyone** can apply and remove preset modifiers to themselves and others. This means, for example, a Bard can apply his inspiration bonuses to his party with a command, or any cool Wizard can drop his most useful spell on the party...

![imcool](https://user-images.githubusercontent.com/10622391/194164506-18d2e541-d76a-4b63-8368-ccf8925e160b.jpg)


 - [Bot Invite.](https://discord.com/api/oauth2/authorize?client_id=1003844628841238588&permissions=277025712192&scope=bot%20applications.commands)

 - [Discord.](https://discord.gg/z2rVRnVjb7)
 
 - [Command reference.](https://github.com/Gellybean/Mathfinder-Bot/wiki/%25Mathfinder-Reference)

This is a big work in progress! I'm sure there are plenty of bugs to work out, and many improvements to make. 

## Getting Started
To create a character, use the `/char` command with the `New` option. Select a name in the `char-name-or-number` field.

![newchar](https://user-images.githubusercontent.com/10622391/193479275-7eeb6257-a91c-44ec-b41f-486731590e95.jpg)

Once you character is created, you can update it with an exported character sheet from a number from different programs, as well as any saved characters from Mathfinder. You can do this by using the `/char-update` command. See the /char reference below for more details.

## Stats & Expressions
Statblocks contain two primary values: Stats and Expressions. 

Each `Stat` contains a base value, as well as a list of bonuses. Each `Bonus` contains a value, a name, and a bonus-type. Together, these are used to accurately calculate the total of any stat when one or many bonuses are applied. (Stacking rules are based on PF1e).

`Expressions` are formulae. These can represent anything from a constant number to an expression of expressions including any number of stats. 

For usability, stats and expressions share a pool of variable names.

**NOTE** — The default character sheet contains a number of both stats and expressions that represent the values you would find on any standard character sheet. This includes ability scores, saves, skills, cmb/cmd, modifiers, etc. Many of these values are important when using certain features, such as preset modifiers, that affect specific variables.

That said, You can completely ignore those features. If you have in-depth homebrew rules that involve custom stats, skills, spells—whatever—you can fully customize your statblock. This means you can add, remove, change any single variable (stats, expressions, rows, grids).

To view these values, use `/var` with the `List-Vars` option.

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

### Mottokrosh's Character Sheet
 - Using the JSON export

**NOTE** — There are specific limitation when parsing different sheets. For instance, not all bonus types may be known for a given stat, and cannot be applied accurately, but the totals should remain correct. This can affect the proper calculation of stacking bonuses. I do my best!

## FAQ

### Does it support things beyond basic actions? (like attack type feats? Vital strike?) (from /r/Elgatee)

For Vital Strike, you would need to multiply the weapon's damage dice (for example, 3d6) like this: `(3d6*2)`. This works just **fine**, but you could get a little fancier and create a variable that holds the multiplier, for example, `VS`. You could then do `(3d6*VS)`. If you were to ever get Improved VS, you could change the single value `VS` from 2 to 3. Of course, if you only have a single attack relying upon Vital Strike, this is overkill.

For something like Power Attack, creating a variable is more useful, since it relies upon a value that scales with your level.

 - Power Attack - hit: `1 + BAB/4`
 - Power Attack - damage : `2 + (BAB/4 * 2)`

Since receiving this question, I've added default expressions representing both: `PA_ATK` and `PA_DMG` respectively.

However, most people are probably going to use Power Attack two-handed. This is where [functions](https://github.com/Gellybean/Mathfinder-Bot/wiki/eval#functions) come in handy.

 - Power Attack - hit - two-handed: `th(PA_ATK)`
 - Power Attack - damage - two-handed: `th(PA_DMG)`
 - Power Attack - hit - off-handed: `oh(PA_ATK)`
 - Power Attack - damage - off-handed: `oh(PA_ATK)`


