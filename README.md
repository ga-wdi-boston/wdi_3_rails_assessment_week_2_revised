# Rails Commands Quiz

Fork, clone, and write your answers directly in this file. Then submit a pull request.


### Question 1

I want to start a new Rails project/app called `BunnyApp`. What command should I type in the terminal?

#### Answer:
<code>rails new BunnyApp --database=postgresql -T</code>


### Question 2

I want to create a new model called `Bunny`, with the following attributes: name (string), color (string), and age (integer). What command(s) should I type in the terminal and/or Sublime? (In your answer, create both a migration and the model file.)

#### Answer:
<code>$ rails g migration Bunny</code>
<p>
  <pre><code>class CreateBunnies &lt; ActiveRecord::Migration
    def change
      create_table bunnies do |t|
        t.string :name, null: false
        t.string :color
        t.integer :age

        t.timestamps
      end
    end
  end</code></pre>
</p>

### Question 3
What does the command in Question 2 do, exactly? What files are created, where are they located, and what does the database look like at this time? Explain.

#### Answer:
<code>$ rails g migration Bunny</code> creates an empty migration file in your db directory of the rails app. 
<br>
<p><pre><code>class CreateBunnies &lt; ActiveRecord::Migration
  def change
    create_table bunnies do |t|
      t.string :name, null: false
      t.string :color
      t.integer :age

      t.timestamps
    end
  end
end</code></pre></p>

* this file defines the columns of your table Bunnies with 3 declared datatypes: name (string), color (string), age (integer)

### Question 4

I want to create a database and make it reflect the new model I created in Question 2. What command(s) should I type in the terminal?

#### Answer:
<code>$ rake db:create db:migrate</code>


### Question 5

I want to look at the actual database that has been created. What command should I type in the terminal?

#### Answer:
<p><pre>
<code>
$ rails db
$ \d
</code>  
</pre>
</p>

### Question 6

I want to see a list of all the URLs available in my app, along with the HTTP requests and controllers associated with them. What command should I type in the terminal?

#### Answer:
<code>rake routes</code>

### Question 7

What line should I add to `config/routes.rb` to create a complete set of RESTful routes for a "bunnies" resource?

#### Answer:
<code>resources :bunnies</code>


### Question 8

According to standard Rails conventions, what directory and filename would the BunniesController be located in, starting from the root of the project?

#### Answer:
<p><pre><code>root > app > controllers > bunnies_controller.rb</code></pre></p>


### Question 9

According to standard Rails conventions, what directory and filename would the "show" view for bunnies be located in, starting from the root of the project?

#### Answer:
<p><pre><code>root > app > views > bunnies > show.html.erb</code></pre></p>


### Question 10

I have worked on my app and finally want to see it in action. What command should I type in the terminal, and where should I navigate to in my browser?

#### Answer:
<p><pre><code>$ rail (s)erver</code></pre></p>


* url: http://localhost:3000



