# The Famous Fifteen Minute Blog
The fifteen minute blog was screencast by [David Heinemeier Hansson](http://david.heinemeierhansson.com/), [DHH](https://github.com/dhh), it has made back at the inception of the Ruby on Rails Project. Using Rails a very early version of Rails, before version 1.0. It can be viewed [on the Ruby on Rails Website](http://weblog.rubyonrails.org/2008/11/27/new-15-minute-blog-video-on-rails-2-2/). It is one of the halmark's of the Ruby on Rails Community. The basic idea of the fifteen blog is show how easy Ruby on Rails web devlopmemt can be.

There is one issue with the fifteen minute blog. It was made in fifteen minutes. It has many issues with security and lack of basic features such as comment moderation. This issues will addressed in reset of this book. Here   

## Posts

### Model

| Field    | Type       |
|----------|------------|
| title    | string     |
| content  | text       |

### Views

#### Blog View
	<% @post.each do |posts| %>
		<div class="single_blog_post">
			<h3><%= post.title %></h3>
			<%= post.content %>
		</div>
	<% end %>
	