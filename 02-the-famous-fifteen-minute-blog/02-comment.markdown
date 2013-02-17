## Comments

## Model

| Field       | Type       |
|-------------|-------|
| name        | string    |
| content     | text        |
| user_id     | integer     |
| post_id     | integer     |
	
## Forms
The form for comments will be on each blog post. The show action.

	<%= form_for(@comment) do |f| %>
		<div class="field>
		  <%= f.label "Comment" %>
		  <%= f.text_field :content %>
		</div>
		
		<div class="field">
		  <%= f.label "Content" %>
		  <%= f.text_area :content %>
		</div>
		
           <div class="action">
             <%= f.submit %>
           </div>
	<% end %>