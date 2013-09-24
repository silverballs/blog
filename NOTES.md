

1. rails generate controller welcome index

2. root to: "welcome#index" in config/routes

3. in config/routes add resources :posts
# the above line creates the standart RESTful actions
for crud

4. rails g controller posts

5. def new action in posts_controller.rb

6. create views/posts/new.html.erb file

7.  