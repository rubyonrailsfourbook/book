# Post Part 2

## Post Restrictions
Only admins should be able to create posts. We will be using the gem [cancan](https://github.com/ryanb/cancan) for this. Cancan is very easy to use as a devloper.

## Defining Who Can Do What
This is called defining abilities. What a you can do is an ability. Declearing who can who is easy with cancan. Use the `can` method to say what people can people and use the `cannot`.

T> ## Need Help Defining Abilites?
T>
T> Check [this page](https://github.com/ryanb/cancan/wiki/Defining-Abilities) on the [cancan wiki](https://github.com/ryanb/cancan/wiki/).

X> ## Extending Permisssions
X>
X> Create roles for serveral roles. Admin, author, editor. You will need to add some fields the user table in order to make this work properly.