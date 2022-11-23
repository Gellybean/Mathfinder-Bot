Changes since last big update...

- Autocomplete—Many fields will now offer suggestions as you type.
- Revamped `/spell`.
  - Removed the `expr` field. 
  - Added an optional `caster-level` field to give you a modified version of the spell output, including targets, range, area-of-effect, and duration. Scaling values in the description will be **bolded**.
- You can now comment expressions by enclosing them inside [ ] brackets. Anything inside will be ignored by the parser.
- Added a keep highest `h` and lowest `l` option to for dice expressions. If you want to roll 4d6 and drop the lowest result, you would use `4d6h3` (keep the highest 3). You could roll 2d20, keeping the lowest roll by doing `2d20l1` (keep the lowest 1).  Using a multiplier with either symbol will split each iteration into separate rolls. This is useful when rolling stat arrays, such as `4d6h3 * 6`.
  - As a note, you can combine this with rerolls (r). For instance, if you wanted to roll 4d6, drop lowest, reroll 1s: `4d6r1h3` (reroll 1s, keep highest 3). 
- Added `is-hidden` option to several commands, which allows anyone else to see embeds and components. Default is hidden.
- Semicolons `;` can now be used to separate expressions. This will let you run multiple evals on a single line.
- You can now enclose variable names in quotes `"`, which allows for spaces. However, Statblock vars will still be converted to upperspaced/underscored ("str score" would be converted to STR_SCORE) before any evalulation is made. This may be used for preset modifiers or other values that can contain spaces.
- Added `/rule`, which is a (searchable) dump for basic rules, terms, conditions, class abilities, etc.
