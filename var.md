### **VAR**

usage: /var `action` `var-name` `value`

-:-

`action`

 - —`Set-Expression` 
   - `var-name` Name of the expression.
   - `value` Expression to create. 

 - —`Set-Row` 
   - `var-name` Row name. This will bring up a modal window, where you can make up to 5 expressions. The syntax is `LABEL:EXPRESSION`. The label is optional—if omitted it will use the expression as the label.

 - —`Set-Grid`
   - `var-name` Grid name. The same as Set-Row except you can specify rows instead of expressions.

 - —`Set-Craft` *EXPERIMENTAL.* This lets you set a mundane item to craft. 
   - `var-name` Item name. 
   - `value` DC to craft.

 - —`List-Vars` Lists all stats, expressions, rows, and grids.

 - —`List-Bonus` Lists all bonuses applied to stats.

 - —`List-Presets` Lists all weapon presets.

 - —`List-Shapes` Lists all available creature shapes.

 - —`List-Crafts` List all active crafts.

 - —`Remove-Variable` Removes a Stat, Expression, Row, or Grid. 
   - `var-name` The variable name to remove.

