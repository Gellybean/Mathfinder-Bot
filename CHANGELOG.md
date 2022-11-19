Changes since last big update...

- Autocomplete—Many fields will now offer suggestions.
- Updated `/spell`. Removed the `expr` field. Added an optional `caster-level` field to give you a modified version of the spell desciption. Scaling values in the description will be **bolded**.
- You can now comment expressions by enclosing them inside [ ] brackets.
- Added a keep highest `h` and lowest `l` option to for dice expressions. If you want to roll 4d6 and drop the lowest result, you would use `4d6h3` (keep the highest 3). You could roll 2d20, keeping the lowest roll by doing `2d20l1` (keep the lowest 1).  Using a multiplier with either symbol will split each iteration into separate rolls, adding up individual rows. This is useful when rolling stat arrays, such as `4d6h3 * 6`.
- Added an optional `is-hidden` field for `/item`. It will still be hidden by default.
- Semicolons `;` can now to used in expressions to separate evaluations. This is useful if you want to calculate two related values at the same time, or apply a set of changes to your stats—as many spells and conditions can affect multiple values at once.
