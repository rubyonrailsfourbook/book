# The Famous Fifteen Minute Blog
The fifteen minute blog was screencast by [David Heinemeier Hansson](http://david.heinemeierhansson.com/), [DHH](https://github.com/dhh), it was made back at the inception of the Ruby on Rails Project. Using a version of Rails before version 1.0. It can be viewed [on the Ruby on Rails Weblog](http://weblog.rubyonrails.org/2008/11/27/new-15-minute-blog-video-on-rails-2-2/). It is one of the hallmark's of the Ruby on Rails Community. The basic idea of the fifteen blog is to show how easy Ruby on Rails web development can be.

There is one issue with the fifteen minute blog. It was made in fifteen minutes. It has many issues with security and lack of basic features such as comment moderation. This issues will addressed in reset of this book.

## Starting the application
I recommend creating a director to store all of your Rails projects in. This will help keep you organized by having all of your work in one place. I store my Rails projects in folder called `rails_projects` and is in my home folder.

    $ mkdir ~/rails_projects 
    $ cd ~/rails_projects

Next we need to create the blog app. This command creates the project and installs all of the included gems.

    $ rails new sample_rails_four_app

Then change into the project.

    $ cd sample_rails_four_app

## Posts resource
In this section we will cover the creation of the posts model. We will also create web user interface to use with the model. This action of combation will create the `PostController`. The controller sits between the view and the model. The controller passes infomation from the model to view for rendering.


### Model
The model is what works with the database to store data in the database. The model also has vaildations.

The title is a string. A string is limited to 255 characters by the database. The content of the post will be stored in a text field in the database. This allows for very long chuncks of content. 


| Field    | Type       |
|----------|------------|
| title    | string     |
| content  | text       |


	$ rails g scaffold post title:string content:text

You can also run this command a bit differently as shown below.

	$ rails g scaffold title content:text

Notice that `title` doesn't have `:string` following it. You can do this since rails assumes that if just put a column name without specifing a type then you want a string column. It's a nice trick to save a few keystrokes. 

Then you need to migrate the database. This will create the posts table in the database.

        $ rake db:migrate

### Views
Views are the presentation layer of the application. The html is sent to the users browsers'. The views are stored in `app/views`. 

#### Blog View / Homepage

	<% @posts.each do |post| %>
		<div class="single_blog_post">
			<h3><%= link_to post.title, post %></h3>
			<%= post.content %>
		</div>
	<% end %>
	
Then in `config/routes.rb`

	root to: 'post#index'

## Routes
When the generator ran rails placed `resources :post` at the top of the `config/routes.rb` file.

Rails uses a covention call REST.

| URL 	   | Action | Description    		           |
|----------|--------|--------------------------------|
| /index   | index  | List all Posts 			       | 
| /show/1/ | show   | List the current post detail   |
| /new     | new    | Create new user                |
| /edit    | edit   | Edit given user                |




| URL 	   		| Action  | Verb      | Description    		 	    |
|---------------|---------|-----------|-----------------------------|
| posts/index   | index   | get       | List all Posts 		 	    | 
| posts/show/1/ | show    | get       | List the current post detail|
| posts/new     | new     | get       | Create new user             |
| posts/1/edit  | edit    | get       | Edit given user             |
| posts/  		| create  | post      | Create Post 				|
| /update       | update  | update    | Update Post                 |
| /posts/1      | destroy | delete    | Delete Given Post           |  








