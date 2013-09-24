

1. rails generate controller welcome index

2. root to: "welcome#index" in config/routes

3. in config/routes add resources :posts
# the above line creates the standart RESTful actions
for crud

4. rails g controller posts