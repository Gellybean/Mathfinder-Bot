### INIT

usage: /init `option` `expr` `isPrivate` `initSave`

`option`
 - —`Add` Using this option, you can add in a single member to initiative. This will automatically roll their init, but they will remain at the bottom until sorted.
   - `expr` The syntax is `NAME:INITBONUS`.
 
 - —`Remove` Remove from initiative.
   - `expr` The index number of the member to remove.
 
 - —`List` List entire initiative.
 
 - —`Roll` Randomly roll all initiative
   
 - —`Sort` Sort initiative.
 
 - —`Move` Move any member to the current turn of initiative.
   - `expr` The index number of the member to move.
 
 - —`Request` Create a request button with a specified bonus players may use to add themselves to initiative. If expr is left blank this will be `1d20+INIT_BONUS`.
   - `expr` 1d20 + expr
 
 - —`New` This will bring up a window where you can enter one init per line. The syntax is the same as the `Add` option. 
 
 - —`Private` Select whether or not the initiative is private. The default value is public.
 
 - —`Load` Load a previously saved initiative.
   - `initSave` Drop your file into this field.
 
 - —`Save` Save current initiative.
 
