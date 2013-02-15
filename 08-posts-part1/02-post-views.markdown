## Post Views

### Some Helper Methods

	def date_format
		"March 4, 2010, 09:00 AM"
	end

### Post Show Page

### Post Listing Page
	<table>
		<thead>
			<tr>
				<th>Title</th>
				<th>Published at</th>
				<th></th>
			</tr>
		</thead>
		<tbody>
			<% post.each do |post| %>
			  <tr>
				<td><%= post.title %></td>
					<td><%= post.published_at %></td>
					<td>
						<%= link_to "Edit", edit_post_url(post) , class: 'btn btn-info' %>
						<%= link_to "Destory", post, method: :delete, class: btn btn-danger' %>
					</td>
				</tr>
			<% end %>
		</tbody>
	</table>
	

### Post Blog Page

	for post in @posts do
		<div class="blog post">
			<h2><%= post.name %></h2>
			<h4>Posted by <%= post.user.name, post.user %></h4>
			<h4><%= post.published_at.stamp(date_format)</h4>
			<%= render_markdown(post.content) %>
		</div>
	end
In order for the `Markdown.render` to work you need to add the follow code to a new file in `app/controllers/application_helper.rb`.

	def render_markdown(text)
		Redcarpet::Markdown.new(Redcarpet::Render::HTML,
        autolink: true, space_after_headers: true).render(text)
	end
This code setups RedCarpet and passes in text to rendered as markdown. This follows for easy formatting.

