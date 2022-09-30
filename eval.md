## **EVALUATE**

usage: /eval `expr` `targets`

-:-

`expr` The expression to evaluate.

`targets` *DM Role Only.* By using @mentions, you can eval multiple active characters at once.

cool?

![eval0](https://user-images.githubusercontent.com/10622391/192032624-f0e56353-731d-4b15-9827-606ee703b1a8.jpg)

more practical

![eval1](https://user-images.githubusercontent.com/10622391/192047953-34581fa4-bf82-4986-93d7-20138f92f437.jpg)

wtf

![eval2](https://user-images.githubusercontent.com/10622391/192032806-774d28bd-acf2-4908-b413-3dcfa75fe8ec.jpg)

cmon

![wtf](https://user-images.githubusercontent.com/10622391/192057007-8601126b-b0b0-489b-bcb1-7fd81ced099b.jpg)



#### Remarks
`/eval` supports many different math operators: `+` `-` `*` `/` `>` `<` `==` `!=` `<=` `>=` `%` `()` `=` `+=` `-=` `*=` `/=` `&&` `||` `?:`. Use `/mf-help` on the bot for more examples.

Dice expressions are also supported within any formula. `1d20` is a valid expression. You can also use rerolls and multipliers. `3d6r1` would "roll" 3 six-sided die, rerolling any dice that come up 1 (the initial roll only). `(3d6*2)` would effectively turn into `6d6`.

Assignment operators (`=`, `+=`, etc) can be used to change the current **base** value of any Stat. The `@` prefix (ex. `@STR_SCORE`) will let you view or utilize the base value of any stat (no bonuses applied).

![bonus](https://user-images.githubusercontent.com/10622391/192063905-989523bc-14ef-4d21-b185-c0e1d84ee1f4.jpg)

To modify bonus values instead, you can use the special `$` operator. Adding a specific bonus to any stat can be done as follows: `STATNAME +$ NAME:TYPE:VALUE`. A name and type are required for determining which bonuses stack. Types can be represented by numbers or names (7 and ENHANCEMENT are identical). To remove a bonus from a stat, you can do: `STATNAME -$ NAME`. This will effectively remove all bonuses with that name from the stat. You can view a specific bonus by doing: `STATNAME $ TYPE`. You can also use `/var List-Bonuses` to see all bonuses applied to all stats.

![types](https://user-images.githubusercontent.com/10622391/192049011-451e78d3-b0db-429c-a74b-75b5fa0f6817.jpg)

The `BASE` type is a special bonus that overrides all other values, including the original base value. This is useful for certain modifiers such as size mods or spells like *feeblemind*, where you need to set a score to a specific value regardless of its current value.

*NOTE* — `/eval` returns integer values only. This comes with some limitations in how evaluations are performed. For example, true and false are represented by 1 and 0 respectively. `TRUE`/`FALSE` are hardcoded variables that can be used for readability. This also applies to all bonus types and their respective numbers.


## Functions
Functions are special commands that (generally) take arguments and return a value.

Reffering to the strength modifier above, you can instead use the `mod` function to do the same thing.

`mod(STR_SCORE)` This will take whatever value is inside the parenthesis and perform the same math operation as above.

You can use these functions in any expression.

  `abs(x)` — Returns the absolute value of x
  
  `clamp(x,y,z)` — Returns value x, clamped between y and z
  
  `if(x,y)` — Returns y if x is TRUE (1), otherwise returns 0
  
  `max(x,y)` — Returns biggest number of x and y
  
  `min(x,y)` — Returns smallest number of x and y
 
  `mod(x)` — Returns the ability score modifier of x
  
  `rand(x,y)` — Returns a random number between x and y
  
  `oh(x)` — offhand, shorthand for `x/2`
  
  `th(x)` — twohanded, shorthand for `x+(x/2)`
  
  `bad(x)` — bad saves, shorthand for `x/3`
  
  `good(x)` — good saves, shorthand for `2+(x/2)`
  
  `tq(x)` — three-quarters, shorthand for `(x+(x/2))/2`
  
  `clearmods()` — clears all bonuses from all stats
