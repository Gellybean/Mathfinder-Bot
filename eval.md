# Evaluate

If you want to call a single formula from you character sheet—such as a saving throw or skill check—often the quickest way to do that is with `eval`. This gives you direct access to the math engine, the core component of Mathfinder.


usage: /eval `expr`


## Basics
Eval requires an active character, where all variables are referenced from.


this

![eval0](https://user-images.githubusercontent.com/10622391/192175946-1b211203-85bf-4692-a608-589583f42afc.jpg)

returns this

![eval](https://user-images.githubusercontent.com/10622391/192175963-8b599fc7-f4c0-4a7c-98d0-2c892625790d.jpg)


Simple, but also useless in the conext of RPGs. Let's say you want to "roll" a d20.

this

![eval2](https://user-images.githubusercontent.com/10622391/192176357-3de125da-d302-4e70-88f4-68d08486413a.jpg)

returns this

![eval3](https://user-images.githubusercontent.com/10622391/192176377-8c9d6eb2-4064-4734-984e-54b073662414.jpg)

When a dice expression is used, it will return an event to let you know what value was rolled. The events are in order of operation.

