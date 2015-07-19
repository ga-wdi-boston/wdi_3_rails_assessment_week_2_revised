# Rails Commands Quiz

Fork, clone, and write your answers directly in this file. Then submit a pull request.

### Question 1

I want to start a new Rails project/app called `BunnyApp`. What command should I type in the terminal?
rails new BunnyApp --database=postgresql -T

### Question 2

I want to create a new model called `Bunny`, with the following attributes: name (string), color (string), and age (integer). What command(s) should I type in the terminal and/or Sublime? (In your answer, create both a migration and the model file.)
rails g model Bunny name color age:integer

### Question 3

What does the command in Question 2 do, exactly? What files are created, where are they located, and what does the database look like at this time? Explain.
NOTE: Although I hinted at it below(..will be used to create the table...), I did not explicily say that the database would be empty.
Creates a timestamped migration file in db/migrate that will be used to create the table Bunny with the specified columns
Creates a file in app/models/bunny
### Question 4

I want to create a database and make it reflect the new model I created in Question 2. What command(s) should I type in the terminal?
rails db:create db:migrate
### Question 5

I want to look at the actual database that has been created. What command should I type in the terminal?
rails db

### Question 6

I want to see a list of all the URLs available in my app, along with the HTTP requests and controllers associated with them. What command should I type in the terminal?
rake routes

### Question 7

What line should I add to `config/routes.rb` to create a complete set of RESTful routes for a "bunnies" resource?
resources :bunny

correction -- resources :bunnies

Duhhhh!!!! - didn't make route name plural!!!!

### Question 8

According to standard Rails conventions, what directory and filename would the BunniesController be located in, starting from the root of the project?
app/controllers/bunnies_controller.rb

### Question 9

According to standard Rails conventions, what directory and filename would the "show" view for bunnies be located in, starting from the root of the project?
app/views/bunnies/show.html/erb

Duhhh!! Typo -- show.html.erb

### Question 10

I have worked on my app and finally want to see it in action. What command should I type in the terminal, and where should I navigate to in my browser?
http://localhost:3000
(btw, the port can be changed by specifying a -p option on rails startup: rails s -p 3005 will start the server  on port 3005. Nice if you want to run a couple of apps at once)
