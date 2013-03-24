# User Model

|Field  			| Type     |
|-------------------|----------|
| name  			| string   |
| email 			| string   |
| url               | string   |
| password_digest	| string   |
| admin 			| boolean  |

## Overview
The user model.

## Stories Covered
* As a user I want my password encrypted before being saved into the database
* As a user I want validations so that I do not forget any important information when creating my account

### Creating the Model
Before we start any major changes we should switch to a topic branch as explained in the git section of this book.

	$ git checkout -b add_users

Next using the table of attributes above we will created the user model

	$ rails g model user name email url password_digest admin:boolean

This will create a model at `app/models/user.rb` and a migration for the user attributes.

Next we need to run the migration to create the database table.

	$ rake db:migrate
	
Then open user model in `app/models/users`. Inside you will find a empty class. This is a good starting place. The next step is to add vaildations.

T> ## Commit early and commit often!
T>
T>	$ git commit -m "Generated user model and migrations were ran."