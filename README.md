# Rails Commands Quiz
## I used my notes and google searches to find answers.

Fork, clone, and write your answers directly in this file. Then submit a pull request.


### Question 1

I want to start a new Rails project/app called `BunnyApp`. What command should I type in the terminal?

rails new BunnyApp
## could also have rails new BunnyApp --database=postgresql -T

1



### Question 2

I want to create a new model called `Bunny`, with the following attributes: name (string), color (string), and age (integer). What command(s) should I type in the terminal and/or Sublime? (In your answer, create both a migration and the model file.)

rails generate model Bunny name color age:integer
## if did migration, then would have: rails g migration CreateBunnies name color age:integer
## or this: touch app/models/bunny.rb (do this in sublime)

1


### Question 3

What does the command in Question 2 do, exactly? What files are created, where are they located, and what does the database look like at this time? Explain.

A Bunny model is created, together with a name attribute of type string, a color attribute that is a string, and an age attribute that's an integer. Those attributes are automatically added to the BunnyApp project.

## the database does not yet exist (because the migration has not been run). The schema is NOT created
0.5


### Question 4

I want to create a database and make it reflect the new model I created in Question 2. What command(s) should I type in the terminal?

rake db:create db:migrate

1

## could also write rake db:setup (this runs rake db:create db:migrate db:seed)


### Question 5

I want to look at the actual database that has been created. What command should I type in the terminal?

rails db

1

## could also do: psql BunnyApp_development



### Question 6

I want to see a list of all the URLs available in my app, along with the HTTP requests and controllers associated with them. What command should I type in the terminal?

rake routes

1



### Question 7

What line should I add to `config/routes.rb` to create a complete set of RESTful routes for a "bunnies" resource?

Rails.application.routes.draw ---> (this will be there when the app is generated)
  resources :bunnies

1



### Question 8

According to standard Rails conventions, what directory and filename would the BunniesController be located in, starting from the root of the project?

app/controllers/bunnies_controller.rb (always plural)

1


### Question 9

According to standard Rails conventions, what directory and filename would the "show" view for bunnies be located in, starting from the root of the project?

app/views/show.html.erb
## correct answer is app/views/bunnies/show.html.erb

0


### Question 10

I have worked on my app and finally want to see it in action. What command should I type in the terminal, and where should I navigate to in my browser?

## also need:
rails s

localhost3000/

#http://mybunnyapp.herokuapp.com

0.5
