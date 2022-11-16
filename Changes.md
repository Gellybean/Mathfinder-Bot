Changes since last big update...

- Autocomplete—Many values will now offer suggestions.
- Updated `/spell`. Removed the previous expr field. You can now provide a value in the `caster-level` field to give you a modified version of the spell desciption. Any scaling values in the description will be bolded.
- You can now comment expressions by enclosing them inside [ ] brackets.
- Added a keep higher and lowest option to dice. If you want to roll 4d6 and drop the lowest dice, you would use `4d6h3` (keep the 3 highest). You roll 2d20, keeping the lowest roll by doing `2d20l1`.  Using a multiplier with either symbol will split each iteration into separate rolls, adding up individual rows. This is useful when rolling ability score arrays.  
