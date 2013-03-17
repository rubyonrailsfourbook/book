## Post Scheduling
Post scheduling will be real simple with the blog. All you have to do is set the published date. The controllers will be set up to only find posts with published_on time that is in the past.

In order to pull only the published posts this query can be used. The `.where` methods accpets SQL. `'published_at <= ?',` is the SQL. The `?` is varabale that is defined after the SQL as a second agurement. In this case `Time.now.utc` which return the UTC time.

	Post.where('published_at <= ?', Time.now.utc)