# Post Part 2

## Stories Covered
* As a user I should not be able to create posts
* As a admin user should be able to create posts
* As a admin user should be able to schedule posts 

## Post Restrictions
Only admins should be able to create posts. We will be using the gem [cancan](https://github.com/ryanb/cancan) for this. Cancan is very easy to use as a developer.

## Defining Who Can Do What
This is called defining abilities. What a you can do is an ability. Declaring who can who is easy with cancan. Use the `can` method to say what people can people and use the `cannot`.

T> ## Need Help Defining Abilities?
T>
T> Check [this page](https://github.com/ryanb/cancan/wiki/Defining-Abilities) on the [cancan wiki](https://github.com/ryanb/cancan/wiki/).

X> ## Extending Permissions
X>
X> Create roles for several roles. Admin, author, editor. You will need to add some fields the user table in order to make this work properly.