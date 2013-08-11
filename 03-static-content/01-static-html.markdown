# Static Content

## Starting Our Blog
In this chapter we will start creating the main blog. So first we need to create the rails app. This will app that will use in the reset of the book. The command below creates a new rails app. It also skips the built in test unit framework, we will be using RSpec and also sets our database to PostgreSQL. The reason for this that Heroku, our hosting provider, uses PostgreSQL It is important that we use the same database in development as in production. This in ensures that there will be no surprises when comes to deploy time. It will also run `bundle install` for us as well to install all of the gems included with rails. If you get an error make sure that

	$ rails new blog --skip-test-unit --database postgresql
	$ cd blog

Next we need to edit the `Gemfile` to make it work for our needs. Please go to

	TODO: Add Link To Gemfile

Next bundle the gems by running:

	$ bundle install

After installing you need to the following command to set RSpec.

	$ rails g rspec:install

After creating the application next we are going to create a git repoository and commit.

	$ git init
	$ git add .
	$ git commit -m "First Commit"

## Static Content
Every site needs static content. Static content is place where such information as contact and about is place. This should not be changed often. So it should be ok if place the content in the source code.

First we need to create a controller and views. We will create some views and a controller for our static content

    $ rails g controller static_content about contact

## Complete Static Pages

These pages are static. The are not changed in any way by rails. Pages like this can be place in `public` folder. For example you can place this code in a file in the `public` in file called `sample_page.html`.

	<html>
		<head>
			<title>Sample Page</title>
		</head>
		<body>
			<h1>This is a truly static page</h1>
		</body>
	</html>

### Issues
This is a very simple HTML page and simple to create. However this is not a good solution. There are a few issues with this approach. The first issue is that layout and navigation, if any, must be updated

#### The Layout
The layout of the site, which we will talk out in the next chapter, will not be applied to these types of pages. They must be given there own style. This can be great.
But, if the goal of these pages is contact and about this might not be the best approach.

#### The Location
Since the advent of the asset pipeline, talked about later in this book, putting files in `public` is sort seems a bit wrong. This a public for error pages and that is about it. That is the attitude given the rails community.

## Mostly Static
The next way is a bit better. This way allows you to keep the same layout of your site very easily.

## REST(ful)
When people first learn about REST they want to do **EVERY** thing RESTfuly.

There is a reason for **NOT** doing this.