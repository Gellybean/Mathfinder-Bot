Changes since last big update...
  - Added a `metamagic` field to /spell. This will allow you to apply one or many metamagics before determining the spell description, as well as any buttons that may be included. Currently supports Empowered, Enlarged, Extended, and Intensified. This feature requires a given caster-level.
  - You can omit the "1" from single die rolls. For example, `d20` instead of `1d20`.
  - Standard Emojis can now be used as variable names 🪄. What have I done?
  - You can now assign expressions in /eval by enclosing a statement inside quotes. For example `TESTEXPR = "1 + 2"` or `BIG_DMG = "5d6 + 🔥`. You can still use the /var command with Set-Expression, which is convenient for modifying existing expressions.
  - Added parsing support for RPG Scribe's .txt output.
  - Removed role restriction for /req. Anyone can create a requested expression—such as a dice roll—which will generate a button that anyone can click.
  - Removed /grid.
    - You can create expression rows with up to 25 buttons (up from 5).
  - Autocomplete now works for the bestiary.
