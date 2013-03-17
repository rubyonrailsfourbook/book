# Post Tags

| Name        | Field    |
|-------------|----------|
| name        | string   |

## Tag Model
This model is the tag. Only the name is the only field along with the `id` field created by rails.

### Validations
In order to create the tag it should have a name

	validates_presence_of :name