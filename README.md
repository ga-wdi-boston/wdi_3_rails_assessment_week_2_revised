# Rails Commands Quiz

Fork, clone, and write your answers directly in this file. Then submit a pull request.

### Question 1

I want to start a new Rails project/app called `BunnyApp`. What command should I type in the terminal?

rails new BunnyApp --database=postgresql -T

### Question 2

I want to create a new model called `Bunny`, with the following attributes: name (string), color (string), and age (integer). What command(s) should I type in the terminal and/or Sublime? (In your answer, create both a migration and the model file.)

rails g migration BreateBunnys name:string color:string age:integer

I would then add app/models/bunny.rb model manually. As a matter of fact, I would rather run command rails g migration BreateBunnys only, and manually specifie the attributes inside the migration file. Inside the model add:
clss Bunny < ActiveRecord::Base
end

rails g model Bunny name color age:integer....
### Question 3

What does the command in Question 2 do, exactly? What files are created, where are they located, and what does the database look like at this time? Explain.

This creates migration file, and does not yet adds to schema.rb file. Database itself is not yet created, everything is prepared for the rake db:create and rake db:migrate.

I was wrong about schema file, I loose one point here

### Question 4

I want to create a database and make it reflect the new model I created in Question 2. What command(s) should I type in the terminal?

rake db:create and then rake db:migrate

rake db:create db:migrate

rake db:setup (rake db:create db:migrate db:seed)


### Question 5

I want to look at the actual database that has been created. What command should I type in the terminal?

start with rails db, it will go into psql, and then type \d. You should see database called bunnys (or maybe bunnies, I woulder how it handles the plural in this case) You can can then type \d bunnys, or even SLECT * FROM bunnys, this ofcourse won't show the entries in the table itself, since we did not run rake db:seed

### Question 6

I want to see a list of all the URLs available in my app, along with the HTTP requests and controllers associated with them. What command should I type in the terminal?

rake routes

### Question 7

What line should I add to `config/routes.rb` to create a complete set of RESTful routes for a "bunnies" resource?

resources :bunnies

RESTful - pattern, used to describe what we expect, expected behavior, compares URLs and HTTP methods, book/1 translates into a retreival of a singular book. Its a pattern to do CRUD. Create, read, update, destroy.

### Question 8

According to standard Rails conventions, what directory and filename would the BunniesController be located in, starting from the root of the project?

app/controllers/bunnies_controller.rb forgot the file, i'll take off half a point

### Question 9

According to standard Rails conventions, what directory and filename would the "show" view for bunnies be located in, starting from the root of the project?

views/bunny/show.html.erb bunny should be plural, take off another half a point

### Question 10

I have worked on my app and finally want to see it in action. What command should I type in the terminal, and where should I navigate to in my browser?

start the server with rails s or rails server. Navigate to localhost:3000/bunnys or localhost:3000/bunnies

