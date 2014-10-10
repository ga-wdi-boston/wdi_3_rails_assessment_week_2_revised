# Rails Commands Quiz

Fork, clone, and write your answers directly in this file. Then submit a pull request.

### Question 1

I want to start a new Rails project/app called `BunnyApp`. What command should I type in the terminal?

CORRECT

rails new BunnyApp --databasepostgresql -T

### Question 2

I want to create a new model called `Bunny`, with the following attributes: name (string), color (string), and age (integer). What command(s) should I type in the terminal and/or Sublime? (In your answer, create both a migration and the model file.)

PARTIALLY CORRECT => CreateBunnies(plural)

There are two ways to do this:

1a. Type in terminal:  rails g model Bunny name:string color:string age:integer
1b. Type in terminal: rake db:create
1c. Type in terminal:  rake db:migrate

2a. In terminal:  rails g migration CreateBunny name:string color:string age:integer.
2b. In text editor create a model named Bunny which inherits from active record
2c. In terminal: rake db: create
2d. In terminal: rake db:migrate



### Question 3

CORRECT => Note I ran migration in answer #2

What does the command in Question 2 do, exactly? What files are created, where are they located, and what does the database look like at this time? Explain.

Creates a database called Bunny with attributes and datatypes as specified in the db folder and if we run the generate model command from the terminal it also gives us the model which is in the app/model folder

### Question 4

WRONG => Forgot to run rake db:create first

I want to create a database and make it reflect the new model I created in Question 2. What command(s) should I type in the terminal?

rake db:migrate


### Question 5

PARTIALLY CORRECT need to run \c

I want to look at the actual database that has been created. What command should I type in the terminal?

rails db
\c
\d nameofdatabase

### Question 6
CORRECT
I want to see a list of all the URLs available in my app, along with the HTTP requests and controllers associated with them. What command should I type in the terminal?

rake routes

### Question 7

CORRECT

What line should I add to `config/routes.rb` to create a complete set of RESTful routes for a "bunnies" resource?

resources :bunnies

### Question 8
WRONG

According to standard Rails conventions, what directory and filename would the BunniesController be located in, starting from the root of the project?
app/controllers/bunnies_controller.rb
bunnies/app/controller_bunnies.rb

### Question 9
WRONG
According to standard Rails conventions, what directory and filename would the "show" view for bunnies be located in, starting from the root of the project?
app/views/bunnies/show.html.erb

app/views/show.html.erb

### Question 10
CORRECT
I have worked on my app and finally want to see it in action. What command should I type in the terminal, and where should I navigate to in my browser?

rails server or rails s



