## Comments Resource
In this section we the setup the comments. The comments will have a form on the bottom of the show page on each post. The comments for each post will also be displayed at the bottom of the post. This will be different from the posts the model as their will not be any dedicated form pages for comments. 
	
### Model

| Field       | Type    |
|-------------|---------|
| content     | text    |
| post_id     | integer |

	$ rails g scaffold comment content:text post:belongs_to

The `post:belongs_to` does a few things. First it creates the `post_id`  field in the database and secondly it addes `belongs_to :post` in the `app/models/comment.rb`.
	
### Forms
The form for comments will be on the show action of the post controller. We are going to place before the list of comments. Reason for this is that user should have to scroll down in order to leave a comment.

	<%= form_for(@comment) do |f| %>
		<div class="field>
		  <%= f.text_field :content %>
		</div>
		
           <div class="action">
             <%= f.submit %>
           </div>
	<% end %>

### Posts Model
 	
	...
	has_many :comments
	....

### Comment Model

	class Comment < ActiveRecord::Base
	  belongs_to :post
	end

### Comment Controller
The scaffold generator generates more than what we need for the comment controller. All the that is need is this. The index, show, new, update, and destroy methods will not used in this app.

	class CommentsController < ApplicationController
		    # POST /comments
	  # POST /comments.json
	  def create
	    @comment = Comment.new(comment_params)

	    respond_to do |format|
	      if @comment.save
	        format.html { redirect_to @comment.post, notice: 'Comment was successfully created.' }
	        format.json { render action: 'show', status: :created, location: @comment }
	      else
	        format.html { render action: 'new' }
	        format.json { render json: @comment.errors, status: :unprocessable_entity }
	      end
	    end
	  end

	  private
	    # Use callbacks to share common setup or constraints between actions.
	    def set_comment
	      @comment = Comment.find(params[:id])
	    end

	    # Never trust parameters from the scary internet, only allow the white list through.
	    def comment_params
	      params.require(:comment).permit(:content, :post_id)
	    end
	end  
	
### Comment Routes
Since we only using the create action on the comment controller we only need the create method on the routes for the commenents resource

	resource :comments, only: [:create]