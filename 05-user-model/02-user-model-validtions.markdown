## Validations
In order the blog work right the blog centrin infomation and in the right format. Checking for this is called vaildtions. When creating validations you need to think about what infomation is needed. In the case of the user model an email and password is needed in order to sign in. So we will require these two values. The method for checking this is called `validates_presence_of`. This is place in the model. Follow by names of the fields to be required.

A long with the presence email address it should be in the correct format.  We will also check that the email is valid. Checking for email format is quite a task so we leave to a gem. We will use a gem called email_validator. With this gem gives us a validation method called `validates_as_email_address` this method works just like `validates_presence_of` message.

	validates_presence_of  :name, :email, :password

This code checks for email address issues. This requires the `validates_as_email_address` gem.

	validates_as_email_address :email


T> ## Commit early and commit often!
T>
T> 	$ git commit -m "Added user vaildtions."
