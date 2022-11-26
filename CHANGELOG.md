Changes since last big update...
  - Added a `metamagic` field to /spell. This will allow you to apply one or many metamagics before determining the spell description, as well as any formulae that may be included.
  - You can now omit the "1" from single die rolls. For example, `d20` vs `1d20`.
  - Standard Emojis can now be used as variable names 🪄. What have I done?
  - Expressions can now be assigned through /eval using the `+#` operator. For example, `TESTEXPR +# "1d20 + 🔥"`. You will need to enclose your statements inside quotes `"` for it to work as intended.
  - Added support for RPG Scribe.
  - Removed active character checks for commands. a `$GLOBAL` name should be set if none already is.
