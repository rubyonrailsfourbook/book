# Post Comments

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


