## Post Views

### Some Helper Methods

    	def date_format
    	  "March 4, 2010, 09:00 AM"
    	end

### Post Show Page

	<h2><%= @post.title %></h2>
	<h4><%= post.user.name, post.user %></h4>
	<h4><%= post.published_at.stamp(date_format)</h4>
	<%= render_markdown(@post.content) %>
	
### Post Listing Page
	<table>
	   <thead>
	     <tr>
	       <th>Title</th>
	        <th>Published at</th>
	         <h4><%= post.published_at.stamp(date_format)</h4>
	     </tr>
	   </thead>
	   <tbody>
	      <% post.each do |post| %>
	        <tr>
	           <td><%= post.title %></td>
	           <td><%= post.published_at %></td>
	           <td>
	             <% if @current_user.admin? %>
	               <%= link_to "Edit", edit_post_url(post) , 
	               		class: 'btn btn-info' %>
	               <%= link_to "Destory", post, 
	               		method: :delete, 
	               class: 'btn btn-danger' %>
	             <% end %>
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


