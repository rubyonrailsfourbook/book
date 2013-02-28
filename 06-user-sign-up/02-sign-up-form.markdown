## Sign Up Form
	<h2>Sign Up!</h2>

	<%= form_for(@user) do |f| %>
		<div class="field">
			<%= f.label :name %>
			<%= f.text_field :name %>
		</div>

		<div class="field">
			<%= f.label :email %>
			<%= f.email_field :email %>
		</div>

		<div class="field">
			<%= f.label :password %>
			<%= f.email_field :password %>
		</div>
	  <%= f.submit %>
	<% end %>
