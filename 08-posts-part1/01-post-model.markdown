# Posts Part 1

| Field                   | Type       |
|-------------------------|------------|
| name 					  | string	   |
| content 				  | text       |
| published_on 			  | datetime   |
| user_id				  | integer    |


## Post Model

### Vaildations

	validates_presence_of :name, content

### Associations
The post belongs to a user.

	belongs_to :user