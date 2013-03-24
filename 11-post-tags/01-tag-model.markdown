# Post Tags

## Stories Covered
* As an admin user I want to create tags with posts
* As I use I want to see a tag cloud to which tags are used
* As a user I want to able to click on tag and see the posts that are tagged the same way

| Name        | Field    |
|-------------|----------|
| name        | string   |

## Tag Model
This model is the tag. Only the name is the only field along with the `id` field created by rails.

### Validations
In order to create the tag it should have a name

	validates_presence_of :name