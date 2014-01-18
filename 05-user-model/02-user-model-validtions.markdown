## Validations
In order the blog work right the blog centrin infomation and in the right format. Checking for this is called vaildtions.

	validates_presence_of  :name, :email

This code checks for email address issues. This requires the `validates_as_email_address` gem.

	validates_as_email_address :email


T> ## Commit early and commit often!
T>
T> 	$ git commit -m "Added user vaildtions."
