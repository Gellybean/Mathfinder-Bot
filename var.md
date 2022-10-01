## **VAR**

usage: /var `action` `var-name` `value`

-:-

`action`

 - —`Set-Expression` 
   - `var-name` Name of the expression. This will bring up a seprate window. If the expression already exists, the space will contain that value.

 - —`Set-Row` 
   - `var-name` Row name. This will bring up a modal window, where you can make up to 5 expressions. The syntax is `LABEL:EXPRESSION`. The label is optional—if omitted it will use the expression as the label.

 - —`Set-Grid`
   - `var-name` Grid name. The same as Set-Row except you can specify rows instead of expressions.

 - —`List-Vars` Lists all stats, expressions, rows, and grids.

 - —`List-Bonus` Lists all bonuses applied to stats.

 - —`List-Weapons` Lists all available weapons.
   - `value` *optional.* You can specify a value to get more detailed information on a single weapon.

 - —`List-Armor` Lists all available armor.
   - `value` *optional.* You can specify a value to get more detailed information on a piece of armor.
 
 - —`List-Shapes` Lists all available creature shapes.
   - `value` *optional.* You can specify a value to get more detailed information on a single shape.

 - —`Remove-Variable` Removes a Stat, Expression, Row, or Grid. 
   - `var-name` The variable name to remove.

