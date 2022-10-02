## **VAR**

usage: /var `action` `var-name`

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

 - —`List-Armor` If var-name is left blank, lists all available armor.
   - `var-name` *optional.* You can specify a name or index number to get the details of an armor.
 
 - —`List-Shape` If var-name is left blank, lists all available creature shapes.
   - `var-name` *optional.* You can specify a name or index number to get the details of a shape.

- —`List-Spell` If var-name is left blank, lists all available spells.
   - `var-name` *optional.* You can specify a name or index number to get the details of a spell.

 - —`List-Weapon` If var-name is left blank, lists all available weapons.
   - `var-name` *optional.* You can specify a name or index number to get the details of a weapon.

 - —`Remove-Variable` Removes a Stat, Expression, Row, or Grid. 
   - `var-name` The variable name to remove.

