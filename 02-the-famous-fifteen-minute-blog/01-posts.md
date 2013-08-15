# The Famous Fifteen Minute Blog
The fifteen minute blog was screencast by [David Heinemeier Hansson](http://david.heinemeierhansson.com/), [DHH](https://github.com/dhh), it was made back at the inception of the Ruby on Rails Project. Using a version of Rails before version 1.0. It can be viewed [on the Ruby on Rails Weblog](http://weblog.rubyonrails.org/2008/11/27/new-15-minute-blog-video-on-rails-2-2/). It is one of the hallmark's of the Ruby on Rails Community. The basic idea of the fifteen blog is to show how easy Ruby on Rails web development can be.


## Starting the Application
I recommend creating a folder to store all of your Rails projects in. This will help keep you organized by having all of your work in one place. I store my Rails projects in folder called `rails_projects` in my home folder. So setup this folder and change into it.

    $ mkdir ~/rails_projects 
    $ cd ~/rails_projects

Next we need to create the blog app. The `rails new` command can help us that at. It creates the project and installs all of the included gems. After it's done change directories into the project. The way to use the `rails new` comamnd is to type `rails new` followed by the name / folder where the rails app will be created. It is important to point out that spaces should not be used in the project name. If you use spaces in the project name it will make your life miserable. Serval commands and funcations of many tools will not work. 

    $ rails new sample_rails_four_app
    $ cd sample_rails_four_app

## Posts resource
In this section we will cover the creation of the posts resource. The resource is a combination of model which helps with storing the posts in the database and views to display the data. Also we will create a controller to sit between the model and view to pass data between the model and thew view.


### Model
The model is what works with the database to the posts data in the database. The model also has validations. These check the data and reject if it doesn't pass them.

The fields on the model will be the following: The title, the title of the post, is a string. A string is limited to 255 characters by ActiveRecord. (ActiveRecrod is the name of library that comes with rails that works with the database, validations, among other things.) PostgreSQL can store more 255 characters in the text field but ActiveRecord throws an exception. (An exception is shown to the user as a Error 500 page.) The content of the post will be stored in a text field in the database. This allows for very long chunks of content which the posts will be.



| Field    | Type       |
|----------|------------|
| title    | string     |
| content  | text       |


    $ rails generate scaffold post title:string content:text

You can also run this command a bit differently as shown below.

    $ rails g scaffold title content:text

Notice that `title` doesn't have `:string` following it. You can do this since rails assumes that if just put a column name without specifying a type then you want a string column. Also `rails generate` can be shorted to `rails g`.  These are nice tricks to save a few keystrokes. 

Next you need to migrate the database. This will create the posts table in the database. This command needs to be ran each time you create a migration. A migration is what changes the database. It can add tables, columns to tables, update column, and add indexes. 

    $ rake db:migrate

### Viewing Pages Localy
In order to view the blog localy you need a web server. Lucky, Ruby and Rails come with one. In order to start it just run `rails server` or if want to save some typing

### Views
Views are the presentation layer of the application. The html is sent to the users; browsers. The views are stored in `app/views`. 

#### Blog View / Homepage
The default view made by the scaffold generator doesn't work to well with blog posts. As shown below. It doesn't look every good and doesn't look like a blog.
![](images/chapter_2/post_index_default.png)

In order to make the homepage look like a blog we need  to make it ourselves. The code below does that. The first line starts the loop. This loops throughe each post and oupts the title in heading thre and the content in a paragraph tag.

	<% @posts.each do |post| %>
		<div class="single_blog_post">
			<h3><%= link_to post.title, post %></h3>
			<p><%= post.content %></p>
		</div>
	<% end %>
	
Next we will set 

	root to: 'post#index'


## Routes
When the generator ran rails placed `resources :post` at the top of the `config/routes.rb` file.

Rails uses a convention call REST.

| URL 	   | Action | Description    		           |
|----------|--------|--------------------------------|
| /index   | index  | List all Posts 			       | 
| /show/1/ | show   | List the current post detail   |
| /new     | new    | Create new user                |
| /edit    | edit   | Edit given user                |




| URL 	   		| Action  | Verb      | Description    		 	    |
|---------------|---------|-----------|-----------------------------|
| /posts/index   | index   | get       | List all Posts 		 	    | 
| /posts/show/1/ | show    | get       | List the current /post detail|
| /posts/new     | new     | get       | Create new user             |
| /posts/1/edit  | edit    | get       | Edit given user             |
| /posts/  		| create  | post      | Create Post 				|
| /posts/update       | update  | update    | Update Post                 |
| /posts/posts/1      | destroy | delete    | Delete Given Post           |  






