# Week 3 Comprehensive Assessment

Fork this repository, update this file to include your answers, and submit a pull request. You may refer to any notes, past projects, or external resources you want. The questions do not have to be completed in order.

### Models

1. I'm creating an app to keep track of bunnies. I already have a `bunnies` table, but I want to create a migration to add a "weight" column to it. What command should I run in my terminal to get started?

rails g migrate AddWeightToBunnies weight:decimal

2. I just realized I misspelled the "weight" column in my migration, but I already ran `rake db:migrate`. What should I do to fix this *without* creating a new migration? Give exact steps and/or commands to run.

- run `rake db:rollback`
- open the existing migration file
- fix spelling errors & save
- run `rake db:migrate`


3. My app has a `Bunny` model, and I want to find bunnies whose `color` attribute is `'white'`, sorted by their `name` attribute. What code could I type in my Rails console to do that?

Bunny.where(color: 'white')


4. Now I want to find the specific bunny whose name is `'George'`. I've made names unique, so there should be only one.

Bunny.find(name: 'George')


5. I want to make sure nobunny, er, I mean nobody, can create a bunny without a name. What code should I add to my `Bunny` model to validate this?

t.string :name, null: false

### Controllers

1. According to standard Rails conventions, what directory and filename would the `BunniesController` be located in, starting from the root of the project?

app/controllers/bunnies_controller.rb


2. I'm in the `show` action of my `BunniesController` and I have the ID of a specific bunny in `params[:id]`. What line should I type to find the bunny with the correct ID, and assign it to a variable that my view can access?

@bunny = Bunny.find(params[:id])


3. In my `update` action I'm trying to update a bunny that I've assigned to a local variable `bunny` using the code `bunny.update(params[:bunny])`, but it gave me a "forbidden attributes error". Why is it telling me this, and what should I do (broadly speaking, no exact code needed) to fix the problem?

You probably don't have access to the attributes. You could try using a private method to get the attributes first, then passing that as the attributes in the bunny.


4. When I create or update a bunny in my controller, how can I find out whether the bunny saved successfully?

Several ways. One is to use binding.pry and call Bunny.all to see if it's there. The other is to run the rails db and find it in the appropriate table.


5. Assuming my bunny saved successfully, what code should I write to redirect the user to the "show" page for the bunny, with a flash message indicating success?

redirect_to bunny_path(@bunny)

### Routes/Views

1. What line should I add to `config/routes.rb` to create a complete set of RESTful routes for a "bunnies" resource?

resources :bunnies
root 'bunnies#index'


2. According to standard Rails conventions, what directory and filename would the "show" view for bunnies be located in, starting from the root of the project?

app/views/show.html.erb


3. I'm in the `index.html.erb` view and I've assigned a variable `@bunnies` to a collection of bunnies. What HTML/ERB code should I write to create an unordered list that shows each bunny's `name` attribute?
<ul>
<% @bunnies.each do |bunny| %>
<li><%= bunny.name %></li>
<% end %>


4. In one of my views, I want to create a link to the "show" path for a specific bunny that I have stored in the variable `bunny`. `rake routes` tells me that I have a standard `bunny_path` helper available. How do I create this link?

<%= link_to bunny.name, bunny_path %>

5. I've created a view partial called `_form.html.erb` and I want to render this partial into my "new" view. What HTML/ERB code should I write to do this?

<%= render 'form' %>

