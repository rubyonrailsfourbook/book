# Static Content

## Static Content
Every site needs static content. Static content is place where such information as contact and about is place. This should not be changed often. So it should be ok if place the content in the source code.
## Complete Static Pages
### How to Create Complete Static Pages
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
This is a very simple HTML page and simple todo. However this is not a good solution. There are a few issues with this approach.

#### The Layout
The layout of the site, which we will talk out in the next chapter, will not be appiled to these types of pages. They must be given there own style. This can be great. 
But, if the goal of these pages is contact and about this might not be the best approach.

#### The Location
Since the advent of the asset pipeline, talked about later in this book, putting files in `public` is sort seems a bit wrong. This a public for error pages and that is about it. That is the attuide given the rails community.
