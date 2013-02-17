## Post Formatting
We will use markdown for the formatting. We will be using a gem called [RedCarpet](https://github.com/vmg/redcarpet)

In order for the `render_markdown` method to work you need to add the follow code to a new file in `app/controllers/application_helper.rb`.

	def render_markdown(text)
		Redcarpet::Markdown.new(Redcarpet::Render::HTML,
        autolink: true, space_after_headers: true).render(text)
	end
	
This code setups RedCarpet and passes in text to rendered as markdown. This follows for easy formatting for posts.