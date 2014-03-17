## Passwords
In this section we will talk about

### Encrpytion
In order store a password it ***MUST*** be encryped in someway. There are better ways than others to store passwords. The best way to store passwords is to use a encrption method that is designed for storing passwords. A good example of a password storage method is BCrypt. Which just so happen be what Rails to store passwords.



T> ## Commit early and commit often.
T>
T>	git commit -m "Added passwords for users"

### The Password Confirmation, or the lack there of
The above code lacks a password confirmation. A password confirmation is when you type in the password twice on sign up.  Here is an explaintion why. The idea is if have them type it two times will help find any flaws in typing or the user forgetting there password. But is this really nessary. If ther e is a "Forgot Password" link is there really any reason have the user type there password twice? The user can just click "Forgot Password" and change the password. Having the user typing the password in twice is a slow down to the user to start using your product. This might be a small slow but makes an impression on the user. By not annoying them with typing their password in second type.

