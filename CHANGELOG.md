Changes since last big update...

- Autocomplete—Many fields will now offer suggestions as you type.
- Updated `/spell`. Removed the `expr` field. Added an optional `caster-level` field to give you a modified version of the spell output, including targets, range, area-of-effect, and duration. Scaling values in the description will be **bolded**.
- You can now comment expressions by enclosing them inside [ ] brackets. Anything inside will basically be ignored by the parser.
- Added a keep highest `h` and lowest `l` option to for dice expressions. If you want to roll 4d6 and drop the lowest result, you would use `4d6h3` (keep the highest 3). You could roll 2d20, keeping the lowest roll by doing `2d20l1` (keep the lowest 1).  Using a multiplier with either symbol will split each iteration into separate rolls. This is useful when rolling stat arrays, such as `4d6h3 * 6`.
- Added `is-hidden` option to several commands. Default is hidden. 
- Semicolons `;` can now be used to separate expressions. This will let you run multiple evals on a single line.
- You can now enclose variable names in quotes `"`, which allows for spaces. However, Statblock vars will still be converted to upperspaced/underscored ("str score" would be converted to STR_SCORE) before any evalulation is made. This may be used for preset modifiers or other values that can contain spaces.
- Added `/rule`. This is a misc. dump for basic rules, conditions, class abilities, etc—generally for a quick reference.
