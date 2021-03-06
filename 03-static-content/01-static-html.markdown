# Static Content

## Starting Our Blog
In this chapter we will start creating the main blog. So first we need to create the rails app. This will app that will use in the reset of the book. The command below creates a new rails app. It also skips the built in test unit framework, we will be using RSpec and also sets our database to PostgreSQL. The reason for this that Heroku, our hosting provider, uses PostgreSQL It is important that we use the same database in development as in production. This in ensures that there will be no surprises when comes to deploy time. It will also run `bundle install` for us as well to install all of the gems included with rails. If you get an error make sure that

	$ rails new blog --skip-test-unit --database postgresql
	$ cd blog

T> # Kestroke Saver
T>
T> `--skip-test-unit` can be expressed as `-T`
T> `--database` can expressed as `-d`
T>
T> So that command be expressed as
T> rails new blog -T -d postgresql

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
Every site needs static content. Static content is the place where information like contact details and about the company is placed. This should not be changed often. So it should be ok if place the content in the source code.


## Complete Static Pages

These pages are static. The are not changed in any way by rails. Pages like this are placed in the `public` folder. For example you can place this code in a file in the `public` in file called `sample_page.html`.

	<html>
		<head>
			<title>Sample Page</title>
		</head>
		<body>
			<h1T>his is a truly static page</h1>
		</body>
	</html>

## Simi-static pages
First we need to create a controller and views. We will create some views and a controller for our static content

    $ rails g controller static_content about contact


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
REST is a pattern used in Rails for the controllers. There are seven actions in the RESTful controller. The following are actions on the REST controller.

| Action Name | HTTP Method | URL              | Description                                |
|-------------|-------------|------------------|--------------------------------------------|
| index       |  GET        | /                | List all records                           |
| show        |  GET        | /show/:id        | Show Details of a record                   |
| new         |  GET        | /new             | Form for Creating a New Record             |
| edit        |  GET        | /edit/:id        | Form for editing as exist record           |
| create      |  POST       | /                | Create a new record with the posted params |
| update      |  PATCH      | /                | Updates a given record                     |
| delete      |  DELETE     | /:id             | Deletes a given record                     |




When people first learn about REST they want to do **EVERY** thing RESTfuly. Yes, most of the blog will dymanic content. However, some parts will be static.

There are reason for **NOT** doing this. The first having RESTful static views adds a lot of complexity to your site. It also creates large load on your database.
