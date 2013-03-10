## Sessions

### Sign In

#### Controller
	{lang="ruby"}
	def new
	end

	def	create
		user = User.find_by_email(params[:session][:email])
	end

#### Views
	{lang="erb"}

	<%= form_tag %>
	<% end %>

### Sign Out