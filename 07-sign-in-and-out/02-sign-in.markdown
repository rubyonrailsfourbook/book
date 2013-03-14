## Sign In

### Controller
	{lang="ruby"}
	def new
	end

	def	create
		user = User.find_by_email(params[:sessions][:email].downcase)
  	if user.try(:authenticate, params[:sessions][:password])
      flash[:success] = "You are now signed in."
  		session[:user_id] = user.id
      redirect_to root_url
  	else
  		flash.now[:error] = "The provided email and password did not match with any user on record."
  		render 'new'
  	end
	end

### Views
	{lang="erb"}

	<%= form_for(:sessions, url: sessions_path) do |f| %>
      <%= f.label :email %>
      <%= f.text_field :email %>

      <%= f.label :password %>
      <%= f.password_field :password %>
      <p></p>
      <%= f.submit "Sign in", class: "btn btn-primary" %>
	<% end %>