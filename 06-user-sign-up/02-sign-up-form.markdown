## Sign Up Form
So now we will start the to create teh sign in form. Rails gives us a whole host of helper methods for creating form. The first form helper method that we will use is `form_for`. The `form_for` method takes in new instance of a model. This is create by calling, in the case of the user, `User.new`. However, we do not put this dircertly in the `form_for` method. We call that line in the controller and assign it to a varible. Such as the example below.

    class UserController < ApplicationController
        def new
        @user = User.new
        end
    end
Then we will use the varible `@user` in the `form_for` method. 

The form for method is method that is block. 
    
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