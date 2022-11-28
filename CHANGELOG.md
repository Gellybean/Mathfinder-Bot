Changes since last big update...
  - Added a `metamagic` field to /spell. This will allow you to apply one or many metamagics before determining the spell description, as well as any buttons that may be included. Currently supports Empowered, Enlarged, Extended, and Intensified. This feature requires a given caster-level.
  - You can now omit the "1" from single die rolls. For example, `d20` instead of `1d20`.
  - Standard Emojis can now be used as variable names 🪄. What have I done?
  - Expressions can now be assigned through /eval using the `+#` operator. For example, `TEST_EXPR +# "1+2"` or `TEST_EXPR +# "d20 + 🔥"`. You will need to enclose your assignments inside quotes `"` for it to work as intended.
  - Added parsing support for RPG Scribe's .txt output.
  - Removed role restriction for `/req`.
  - Removed `/grid`. You can now create as many as 25 buttons in a single `/row`. You can create them by calling `/var`, selecting the Set-Row action.
