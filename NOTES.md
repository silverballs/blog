

1. rails generate controller welcome index

2. root to: "welcome#index" in config/routes

3. in config/routes add resources :posts
# the above line creates the standart RESTful actions
for crud

4. rails g controller posts

5. def new action in posts_controller.rb

6. create views/posts/new.html.erb file

7.  add form to above page:
<!-- 
<%= form_for :posts do |f| %>
	<p>
		<%= f.label :title%><br>
		<%= f.text_field :title%>
	</p>
	<p>
		<%= f.label :text%><br>
		<%= f.text_field :text%>
	</p>

	<p>
		<%= f.submit %>
	</p>
<% end %> -->

8. make the above form's first line <%= form_for :posts, url: posts_path  do |f| %>

9. def a create action in posts controller and place the following in the definition:
render text: params[:post].inspect

10.  in terminal do rails g model Post title:string text:text and run rake db:migrate

In order to save data in the controller change posts_controller to this:
class PostsController < ApplicationController

def new
end

def create
	@post = Post.new(post_params)
	@post.save
	redirect_to @post
end

private 

	def post_params
		params.require.(:post).permit(:title, :text)
	end

end


