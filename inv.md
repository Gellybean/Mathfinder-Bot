### **INVENTORY**

usage: /inv `action` `item` `qty` `attachment`

-:-

![inv](https://user-images.githubusercontent.com/10622391/192052270-6623db24-1040-4316-a250-fcfa20adec87.jpg)

`action`

- —`Add` Add one or many items to your active character's inventory. Leave all other fields blank to bring up a window where you can input a list of items.
  - `item` *optional* The syntax for adding an item is `NAME:WEIGHT:VALUE`. For example, `Sword:5:10` would add a Sword of 5 weight and a value of 10. Only name is required.
  - `qty` *optional.* How many to add. Default is 1.

- —`Import` Import a list of items. CAUTION—This will **REPLACE** any existing list. If you want to add many items, use the `Add` action. You can copy/paste your text file into the subsequent modal.
  - `attachment` A text file containing one item per line.

- —`Export` Export the current list to a text file.

- —`Remove` Remove an item from your list.
  - `item` The name or index number of the item. If a name is given, it will remove the first occurence any matched value.
  - `qty` The number of the specified items to remove.

- —`List` List your current inventory.
