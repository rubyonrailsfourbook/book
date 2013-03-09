## Sessions

### Sign In

#### Controller

	def new
	end

	def	create
		user = User.find_by_email(params[:session][:email])
	end

#### Views

### Sign Out