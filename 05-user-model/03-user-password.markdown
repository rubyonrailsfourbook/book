## Passwords
To start the passwords just place `has_secure_password` in your user model. Then you need to validate that if the password field is filled in on forms. you need to do is add the `:password` attribute added to `validates_presence_of`.

	validates_presence_of :name, :email, :password

T> ## Commit early and commit often.
T>
T>	git commit -m "Added passwords for users"

### The Password Confirmation, Lack there of
The above code lacks a password confirmation. A password confirmation is when you type in the password twice on sign up.  Here is an explaintion why. The idea is if have them type it two times will help find any flaws in typing or the user forgetting there password. But is this really nessary. If ther e is a "Forgot Password" link is there really any reason have the user type there password twice? The user can just click "Forgot Password" and change the password. Having the user typing the password in twice is a slow down to the user to start using your product. This might be a small slow but makes an impression on the user. By not annoying them with typing their password in second type. 

## End of Chapter
Time to merge the `add_users` branch

	$ git checkout master
	$ git merge add_users

