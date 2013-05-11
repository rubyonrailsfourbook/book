# Post Comments

## Stories Covered
* As I user I want vaildtions to that I don't see blank comments

| Field                   | Type       |
|-------------------------|------------|
| content				  | text 	   |
| user_id 				  | integer    |
| post_id	 			  | integer	   |
| user_remote_ip		  | string     |
| user_agent			  | string     |


## Comment Model

### Validations

	validates_presence_of :content

### Associations

	belongs_to :post

	belongs_to :user

The comment belongs to the post at it was left on. 

The comments also belongs to the user that created it.


