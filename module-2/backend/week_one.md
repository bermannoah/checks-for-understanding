## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!). 

Note: When you're done, submit a PR. 

1. List the five common HTTP verbs and what the purpose is of each verb.
 - GET - loads/reads the requested thing
 - POST - sends data to the server (create)
 - PUT - updates existing data
 - PATCH - updates existing data
 - DELETE - destroys / deletes existing data
2. What is Sinatra? 
 - Sinatra is a "domain specific language" - helps communicate properly with the server
4. What is MVC?
 - Model View Controller - it's a pattern for development - a controller that (described simply) tells everything where to go, a series of views that render data for the user, and models that hold the internal logic.
5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
  - it keeps things operating as people are used to - both for fellow developers who have to use our code and the end-users
6. What types of variables are accessible in our view templates without explicitly passing them?
  - instance variables
7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?
  
  ```ruby
  get '/horses' do
    @count = 1
    erb :index
  end
  ```

8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed`?
  erb :index, :locals => {:name => params[:name]}

9. What's the purpose of ERB?
  - gives us the ability to easily insert the results of ruby methods into our views
10. Why do I need a development AND test database?
  - testing takes less time if we're able to quickly modify small amounts of data in test, plus we don't want to expose "live" or potentially important data to un-polished things we're testing. (goes without saying to keep these db's separate from production!
11. What's responsive design?
  - essentially: designing for as many screen-sizes as possible, (hopefully) without losing functionality
12. What is CRUD and why is it important?
  - CRUD stands for Create Read Update Destroy/Delete - at its most basic, it's a nearly-universal pattern for the way users expect to interact with websites.
13. What does HTTP stand for? 
  - Hyper Text Transfer Protocol 
14. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
  - <% ruby %> - runs the thing
  - <%= ruby %> - runs the thing, prints the thing
15. What's an ORM?
  - ORM is object relational mapper - it essentially wraps a database in an object oriented language, making it easier to access and manipulate
16. What's the most commonly used ORM?
  - ActiveRecord (?)
17. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
  - See all restaurants - /restaurants - GET - gives overview of everything
  - See one restaurant - /restaurants/:id - GET - shows just the one thing
  - See form to enter new restaurant - /restaurants/new - GET - just shows the new-restaurant form
  - Click submit to save new restaurant - /restaurants - POST - makes a new restaurant (should save to DB)
  - See form to edit - /restaurants/id/edit - GET - shows form to edit
  - Click submit to save restaurant - /restaurants/:id - PUT or PATCH - updates existing task
  - Delete a task - /tasks/:id - DELETE - deletes task!
18. What's a migration? 
  - a migration is a file that lets you modify or create a DB table
19. When you create a migration, does it automatically modify your database?
  - no, you need to at least run (for example) rake db:migrate
20. How does a model relate to a database?
  - a model provides logic for manipulating the info in the database, as well as describing the relations between various pieces of information in the DB
