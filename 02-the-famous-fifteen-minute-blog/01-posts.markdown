# The Famous Fifteen Minute Blog

## Posts

### Model

| Field    | Type       |
|----------|------------|
| title    | string     |
| content  | text       |

### Views

#### Blog View
	@post.each do |posts|
		<div class="signal_blog_post">
			<h3><%= post.title %></h3>
			<%= post.content %>
		</div>
	end