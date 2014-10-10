# Rails Commands Quiz

Fork, clone, and write your answers directly in this file. Then submit a pull request.

### Question 1

I want to start a new Rails project/app called `BunnyApp`. What command should I type in the terminal?

rails new BunnyApp --database=postgresql -T

### Question 2

I want to create a new model called `Bunny`, with the following attributes: name (string), color (string), and age (integer). What command(s) should I type in the terminal and/or Sublime? (In your answer, create both a migration and the model file.)

rails g migration Bunny name color age:integer

In  sublime we can create the model file called bunny.rb and manually create the model and type:

class Bunny < ActiveRecord::Base
end

### Question 3

What does the command in Question 2 do, exactly? What files are created, where are they located, and what does the database look like at this time? Explain.

The command in Q2 created a migration file which has no effec to db without running the command 'rake db:migrate' on terminal. After we run this command it will create a table called (probably) bunnies and columns specified in Q2.

### Question 4

I want to create a database and make it reflect the new model I created in Question 2. What command(s) should I type in the terminal?

rake db:create
rake db:migrate

### Question 5

I want to look at the actual database that has been created. What command should I type in the terminal?

rails db

### Question 6

I want to see a list of all the URLs available in my app, along with the HTTP requests and controllers associated with them. What command should I type in the terminal?

rake routes

### Question 7

What line should I add to `config/routes.rb` to create a complete set of RESTful routes for a "bunnies" resource?

resources :bunnies

### Question 8

According to standard Rails conventions, what directory and filename would the BunniesController be located in, starting from the root of the project?

/BunnyApp/app/controllers/bunnies_controller.rb

### Question 9

According to standard Rails conventions, what directory and filename would the "show" view for bunnies be located in, starting from the root of the project?

/BunnyApp/app/views/show.html.erb

Wrong

Correct Answer: /BunnyApp/app/views/bunnies/show.html.erb

### Question 10

I have worked on my app and finally want to see it in action. What command should I type in the terminal, and where should I navigate to in my browser?

rails s

if you type root 'bunnies#index' it just ok to type localhost:3000, but if you didnt you should type localhost:3000/bunnies



