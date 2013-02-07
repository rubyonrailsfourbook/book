## Post Views

### Some Helper Methods

	def date_format
		"March 4, 2010, 09:00 AM"
	end

### Post Show Page

### Post Listing Page
	for post in @posts do

	end
### Post Blog Page

	for post in @posts do
		<div class="blog post">
			<h2><%= post.name %></h2>
			<h4>Posted by <%= post.user.name, post.user %></h4>
			<h4><%= post.published_at.stamp(date_format)
		</div>
	end