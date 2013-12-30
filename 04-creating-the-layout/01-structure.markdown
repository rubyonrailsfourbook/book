# Creating the Layout

This section will cover how to make the blog look nice. The Ruby on Rails Four Book is not a book on web design. However this book will still do a minor look into CSS. Besides, it doesn't hurt have a nice looking application when working on it. 

## Stories Covered in this Chapter

* As a user I want to be able to have a nice layout

In this chapter will create a feature branch to isolate our changes.

	$ git checkout -b creating_the_layout

## Structure
It's important when working with a web application to have an outline of your final product. In order to do this book will use a mockup. A mockup is drawing of what the web page will look like. Below is the mockup for the homepage for the blog.


![](images/chapter_4/homepage.png)


To start the layout make sure that your `Gemfile` is updated to the lastest here. Next you need to move `app/assets/stylesheets/application.css` to `app/assets/stylesheets/application.css.scss`. In order to this we will need to move with the `git mv` command. You could move via drag and drop or just `mv` command but this would not track the changes in git. In order track the changes in git you need to `git mv` like so:


	$ git mv app/assets/stylesheets/application.css app/assets/stylesheets/application.css.scss

Next we need to add bootstrap to the our css file. You can do this by adding this line to your `app/assets/stylesheets/application.css.scss`. Please note that if you are having issues with `@import` then make sure that move the file to the `.scss` extension. 

	@import 'twitter/bootstrap';
  


  