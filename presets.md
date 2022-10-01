## **PRESET-ARMOR**

usage: /preset-armor `number-or-name` `enhancement`

-:-

`number-or-name` The name or index number associated with it (use /var List-Armor to see a comprehensive list).

`enhancement` *optional.* The enhancement bonus (if any) to AC.

![hara](https://user-images.githubusercontent.com/10622391/192118521-60e4c411-a50b-49dd-8793-9ffb6e9bf74d.jpg)

#### Remarks
This command will apply the stats gained from a specific set of armor (or a shield) to an active character. For shields, this applies a shield bonus to AC and skill check penalties. For armor, this applies an armor bonus to AC, skill check penalties, and max AC gained from Dexterity. It will attempt to remove any previous armor or shield bonuses respectively.


## **PRESET-MODIFIER**

usage: /preset-mod `action` `mod-name` `target`

-:-

`action`

 - —`Add` Add the following mod-name.
 - —`Remove` Remove the following mod-name.

`mod-name` Name of the modifier (use /var List-Mods for a comprehensive list).

`target` *optional.* Target or targets using @mentions. Leave blank to target yourself.

![presetmod](https://user-images.githubusercontent.com/10622391/193415642-83cfe538-c638-4474-ba0b-7054e84f2b19.jpg)

![mod1](https://user-images.githubusercontent.com/10622391/192043649-46aa7dcc-0f48-4c53-b1a5-5d4198febdc4.jpg)


### Remarks
This command will add or remove a modifier to your current character. Some modifiers contain sub-options, such as `BEAST_SHAPE` or any spell that scales with caster level. These options generally appear as buttons.



## **PRESET-SHAPE**

usage: /shape `number-or-name` `hit-mod` `multi-attack`

-:-

`numer-or-name` The name or index number associated with it (use /var List-Shapes to see a comprehensive list).
 
`hit-mod` The modifier used for hitting.

`multi-attack` *optional.* Set to true if you possess the `Multiattack` feat. This will adjust the penalty on your secondary attack.
 
### Remarks
`/shape` is meant to be used together with a polymorph `/preset-mod`, such as `BEAST_SHAPE`. This will generate the attacks (primary and/or secondary) and natural weapons associated with a particular creature's shape. In addition, it will list any speeds, senses, or special abilities you may receive from taking the creature's shape. Be sure to follow the particular spell's allowances, as many creatures are listed with their maximum possible features.

![shape](https://user-images.githubusercontent.com/10622391/192065898-00161ce4-7775-4b49-b7bf-34c11d8631d3.jpg)


## **PRESET-SPELL**

usage: /preset-spell `number-or-name` `expr`

-:-

`number-or-name` The name or index number of the spell. When the `expr` value is ignored, it will simply list the spell's info without any character-specific evaluations.

`expr` *optional.*  For this option to work properly, you need: 
 - `CL_CLASSNAME` A stat representing your caster level with the desired class.
 - `MOD_CLASSNAME` An expression representing your spellcasting ability score modifier.

**The class name is arbitary**, but needs to be the same for all variables you intend to use.

![clpsy](https://user-images.githubusercontent.com/10622391/193384381-c62a8e75-21e6-4557-b5ec-495258ff8060.jpg)
![exprpsy](https://user-images.githubusercontent.com/10622391/193384422-1a2db1f8-2dc6-493d-83b8-2de25c8c8f86.jpg)

The syntax is `SPELLLEVEL:CLASSNAME`. This will use the aforementioned variabled to calculate you Difficulty Class and Caster Level for the spell.
 
![psy](https://user-images.githubusercontent.com/10622391/193386057-bf25a232-12b3-4eed-a4cb-754ec334422e.jpg)

![mt](https://user-images.githubusercontent.com/10622391/193384050-16149f05-4a81-4bc4-8992-1a82da112e45.jpg)

If you have other modifiers that increase DC/CL, such as Spell Focus or that expensive Ioun stone (you know the one I'm talking about), there are built-in additions you can use. For example, you can modify your `CL_BONUS` stat, and it will automatically be added to you Caster Level. School, Subschool, and Descriptors are considered for each spell; For DCs and CLs, you can use variables like `DC_EVOCATION` and `CL_EVOCATION` respectively. Other examples include `DC_FIRE`, `CL_MIND_AFFECTING`.



## **PRESET-WEAPON**

usage: /preset-weapon `number-or-name` `hit-mod` `damage-mod` `hit-bonus` `dmg-bonus` `size`

-:-

`number-or-name` The name or index number associated with it (use /var List-Weapons to see a comprehensive list).

`hit-mod` *optional* The modifier used for hitting. Default is STR.

`damage-mod` *optional* The modifier used for damage. Default is None.

`hit-bonus` *optional.* The bonus to hit.

`dmg-bonus` *optional.* The bonus damage.

`size` *optional.* The size of the character. If left blank, it will check the character's Stackblock for size. If none is found, it will default to medium.


![preset](https://user-images.githubusercontent.com/10622391/192030455-2149b615-ea3f-4663-b55d-5d8a56846b8f.jpg)

![weapon](https://user-images.githubusercontent.com/10622391/192163817-021abd3f-c883-40d6-a021-751cd17c653e.jpg)


### Remarks
You can use `/preset-save` with a `name` to save the last generated preset to your active character sheet.

![gsp1](https://user-images.githubusercontent.com/10622391/193103489-75e9736b-2517-4b50-8d4e-1587e9daaa77.jpg)


