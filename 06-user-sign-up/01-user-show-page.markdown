# User Sign Up

## Stories Covered
* As a User I want to able to Sign Up for the site


In order to for our readers to comment on posts you need to sign up. This chapter will work on this task. Whenever making large changes or large additions it is a good idea to create a topic branch.

	$ git checkout -b users_views

The first thing is to create the controllers. This will also create the views we define.

	$ rails g controller users index show new edit

This command will create a restful controller and blank views.

## User Show Page
This a profile page for each user. There will two types. The first is for admins. The admin menu will posts and comments. While the non-admin profile will show only comments. Since these have not been created yet we will add these later.

T> ## Commit early and commit often!
T>
T>  $ git commit -m "Added users controllers and views"