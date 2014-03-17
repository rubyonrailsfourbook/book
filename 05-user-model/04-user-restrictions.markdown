## User Restrictions
As normal user I should not be able to edit another user's password or email. In this section I will cover stop keep your user model secure. The concepts used in this lesson will be used in the rest of this book to keep things locked down.

### Controllers
The first part of secureing will be started in the controller for users. Rails provides us with some simple methods for protecting data for unauthorized access. In this section we will be using the `@current_user` variable which stores the current user that is signed in. Later in this will use `@current_user` with methods that come assoctations in rails.

First we will start in the show action. The show action shows the details for the given the model. For example the show page for the user with the id of 1 would be `/users/1`. The default method for getting the user variable for the show method is:

  @user = User.find(params[:id])


However, this is not secure at all. All an attack, or anyone else, has to to is change the number to a differnt one to see what details of the user is. For example say I am user id 1 and you are number 2. If I want to look up your user account details all I would have to do is change the id from 1 to a 2. Just like that I now have access to your account data.

## End of Chapter
Time to merge the `add_users` branch to the master.

	$ git checkout master
	$ git merge add_users
