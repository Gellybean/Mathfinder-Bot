# Evaluate

If you want to call a single formula from you character sheet—such as a saving throw or skill check—often the quickest way to do that is with `/eval`. This gives you direct access to the math engine, the core component of Mathfinder.


usage: /eval `expr`


## Basics
Eval requires an active character, where all variables are referenced from.


this

![eval0](https://user-images.githubusercontent.com/10622391/192175946-1b211203-85bf-4692-a608-589583f42afc.jpg)

returns this

![eval](https://user-images.githubusercontent.com/10622391/192175963-8b599fc7-f4c0-4a7c-98d0-2c892625790d.jpg)


Simple, but not very useful. Here's how you "roll" a d20.

this

![eval2](https://user-images.githubusercontent.com/10622391/192176357-3de125da-d302-4e70-88f4-68d08486413a.jpg)

returns this

![eval3](https://user-images.githubusercontent.com/10622391/192176377-8c9d6eb2-4064-4734-984e-54b073662414.jpg)

When a dice expression is used, it will return an event to let you know what value was rolled. The events are in order of operation.

Now we can add a modifier to the roll.

  `1d20 + STR_SCORE` This would roll a twenty-sided die and add your STR_SCORE to the total. Of course, that's silly, since you would want the modifier instead.
  
  `(STR_SCORE - 10) / 2` With this, we can get the modifier value and then do `1d20 + (STR_SCORE - 10) / 2`.
  
  More practically, you would want to store this modifier in its own value. You can do this by using the `/var` command with the `Set-Expression` option. You would then give it a name like so:
  
  ![expr1](https://user-images.githubusercontent.com/10622391/192177394-3fcd6d21-d22e-4956-bec8-d6cb79a7bbc9.jpg)

Keep in mind, these are only examples. Basic values like these are already set in the default Pathfinder sheet. The general goal of Mathfinder is minimal setup, with the option for customization.


## Functions
Functions are special commands that generally take arguments and return a value.

Reffering to the strength modifier above, you can instead use the `mod` function to do the same thing.

`mod(STR_SCORE)` This will take whatever value is inside the parenthesis and perform the same math operation as above.

You can use these functions in any expression.

  `abs(x)` — Returns the absolute value of x
  `clamp(x,y,z)` — Returns value x, clamped between y and z
  `if(x,y)` — Returns y if x is TRUE (1), otherwise returns 0
  `max(x,y)` — Returns biggest number between x and y
  `min(x,y)` — Returns smallest number between x and y
  `mod(x)` — Returns the ability score modifier of x
  `rand(x,y)` — Returns a random number between x and y
  `oh(x)` — offhand, shorthand for x/2
  `th(x)` — twohanded, shorthand for x*(x/2)
  `bad(x)` — bad saves, shorthand for x/3
  `good(x)` — good saves, shorthand for 2+(x/2)
  `tq(x)` — three-quarters, shorthand for (x+(x/2))/2
  `clearmods()` — clears all bonuses from all stats
