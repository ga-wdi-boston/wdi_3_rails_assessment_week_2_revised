# Rails Commands Quiz

Fork, clone, and write your answers directly in this file. Then submit a pull request.

### Question 1

I want to start a new Rails project/app called `BunnyApp`. What command should I type in the terminal?

rails new BunnyApp --database=postgresql -T

CORRECT

### Question 2

I want to create a new model called `Bunny`, with the following attributes: name (string), color (string), and age (integer). What command(s) should I type in the terminal and/or Sublime? (In your answer, create both a migration and the model file.)

rails generate model Bunny name color age:integer
rails generate migration CreateBunnies name color age:integer
(then modify migration file as needed in Sublime)
rake db:migrate

CORRECT

### Question 3

What does the command in Question 2 do, exactly? What files are created, where are they located, and what does the database look like at this time? Explain.

Line 15 creates bunny.rb, the model file for Bunny, in app/models. Line 16 sets up the first migration, which includes a table in the DB for Bunny, with the attributes of name, color, and age. The resultant migration file is found in db/migrate. The database will not be created until we run rake db:create (see next question)

PARTIALLY CORRECT? - missing info about schema file; incomplete description of what "rails g model" does

### Question 4

I want to create a database and make it reflect the new model I created in Question 2. What command(s) should I type in the terminal?

rake db:create db:migrate

CORRECT (rake db:setup is also acceptable)

### Question 5

I want to look at the actual database that has been created. What command should I type in the terminal?

rails db
\d Bunny

CORRECT

### Question 6

I want to see a list of all the URLs available in my app, along with the HTTP requests and controllers associated with them. What command should I type in the terminal?

rake routes

CORRECT

### Question 7

What line should I add to `config/routes.rb` to create a complete set of RESTful routes for a "bunnies" resource?

resources :bunnies

CORRECT

### Question 8

According to standard Rails conventions, what directory and filename would the BunniesController be located in, starting from the root of the project?

app/controllers/bunnies_controller.rb

CORRECT

### Question 9

According to standard Rails conventions, what directory and filename would the "show" view for bunnies be located in, starting from the root of the project?

app/views/bunnies/show.html.erb

CORRECT

### Question 10

I have worked on my app and finally want to see it in action. What command should I type in the terminal, and where should I navigate to in my browser?

rails s  (type in terminal to start server)
navigate to localhost:3000 in browser

CORRECT
