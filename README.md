# Rails Commands Quiz

Fork, clone, and write your answers directly in this file. Then submit a pull request.

### Question 1

I want to start a new Rails project/app called `BunnyApp`. What command should I type in the terminal?

rails new BunnyApp --database=postgresql -T

### Question 2

I want to create a new model called `Bunny`, with the following attributes: name (string), color (string), and age (integer). What command(s) should I type in the terminal and/or Sublime? (In your answer, create both a migration and the model file.)

rails g model Bunny name color age:integer, is the cheaty answer that David has told us not to use

Was I supposed to specify what you'd need to write in the model?
class Bunny < ActiveRecord::Base
end

### Question 3

What does the command in Question 2 do, exactly? What files are created, where are they located, and what does the database look like at this time? Explain.

it creates app/models/Bunny.rb and db/migrate/*insert long number here*_create_bunnies.rb
The database is non-existent unless you separately created it beforehand
(Looked up to get the exact path right for the migrate)

### Question 4

I want to create a database and make it reflect the new model I created in Question 2. What command(s) should I type in the terminal?
rake db:create

did not read second half of the question.

rake db:create
rake db:migrate
	or
rake db:create db:migrate
	or
rake db:setup

### Question 5

I want to look at the actual database that has been created. What command should I type in the terminal?
rails db

### Question 6

I want to see a list of all the URLs available in my app, along with the HTTP requests and controllers associated with them. What command should I type in the terminal?
rake routes

### Question 7

What line should I add to `config/routes.rb` to create a complete set of RESTful routes for a "bunnies" resource?
resources :bunnies

(RESTful routes is a design pattern that basically says how to design your URLs for a basic CRUD app- for example if you go to http://myapp.com/book/1 you can expect to see the show page for a single book, and http://myapp.com/books is for a list of all the books)
### Question 8

According to standard Rails conventions, what directory and filename would the BunniesController be located in, starting from the root of the project?
app/controllers/bunnies_controller.rb

### Question 9

According to standard Rails conventions, what directory and filename would the "show" view for bunnies be located in, starting from the root of the project?
app/views/bunny/show.html.erb

so it has to be bunnies folder? I thought it had to be bunny.

### Question 10

I have worked on my app and finally want to see it in action. What command should I type in the terminal, and where should I navigate to in my browser?

rails s or rails server

localhost:3000
