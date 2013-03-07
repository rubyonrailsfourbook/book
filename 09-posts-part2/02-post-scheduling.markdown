## Post Scheduling
Post scheduling will be real simple with the blog. All you have to do is set the published date. The controllers will be set up to only find posts with published_on time that is in the past.

In order to pull only the published posts.

	Post.where(where('published_at <= ?', Time.now.utc))