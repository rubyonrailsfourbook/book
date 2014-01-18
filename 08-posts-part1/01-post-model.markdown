# Posts Part 1

| Field                   | Type       |
|-------------------------|------------|
| name 					          | string	   |
| content 				        | text       |
| published_on 			      | datetime   |
| user_id				          | integer    |

## Stories Covered
* As a user I want to able view posts in blog layout
* As a user I want a one post on page so that I can read the post and leave a comment

## Post Model

### Vaildations

	validates_presence_of :name, content

	validates_length_of :content, minimum: 255

### Associations
The post belongs to a user.

	belongs_to :user