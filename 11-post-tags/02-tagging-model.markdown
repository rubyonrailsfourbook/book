## Tagging Model
This model will used for each tag on each post.

| Name        | Field    |
|-------------|----------|
| post_id     | integer  |
| tag_id	  | integer  |

### Associations
	
	belongs_to :post

	belongs_to :tag
