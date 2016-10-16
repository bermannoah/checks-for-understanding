## Week Two - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!). 

Note: When you're done, submit a PR. 

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
 - ActiveRecord is a way to use Ruby to talk to databases. It lets you abstract out database logic to more readable, easily usable ruby methods.
2. What is a migration?
  - It's when a bunch of geese... I mean it's a file you can use when need to create or update or delete tables in a database. 
3. How does a table relate to a model?
  - A table holds the raw data that the model's logic can iterate over.
4. What kind of methods are `belongs_to`, and `has_many`? (i.e. class or instance) Give an example.
  - belongs_to and has_many are class methods. As an example: a library has_many books, while a book belongs_to a library.
5. What do they allow you to do?
  - they let you establish relationships between objects in different tables. Sounds simple, is really powerful. It makes it easier to change things - rather than having to manually adjust the library's name for every book, you just change it once and it affects all of them.
6. What's the difference between agile workflow and waterfall method?
  - waterfall is an older method for handling workflow - essentially doing each step of the software development process in methodical order. This can be compared with agile workflow, where you're constantly iterating in small steps made up of each element of development.
7. What is the difference between `#new` and `#create`?
  - #new makes a new object but does not save it, #create makes AND saves a new object.
8. At a basic level, what does cURL allow you to do?
  - at a basic level cURL allows you to transfer data to/from a server
9. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.
  - a student belongs_to a teacher, a teacher has_many students.
  
  Teachers -> has_many Students
  (id, name)
  Students -> belongs_to Teachers
  (id, name, teacher_id)
10. Define foreign key, primary key, and schema.
  - a foreign key is (almost always) a numerical id tying an object on one table to an object on another
  - a primary key is a unique identifier for an object in a table
  - a schema is a file that provides a high-level overview of a database's structure
11. Describe the relationship between a foreign key on one table and a primary key on another table.
  - a foreign key on one table essentially points to a primary key on another table, allowing the program to identify the object inteded to be accessed
12. What are the parts of an HTTP response?
  - status code, header, body
13. `Rack::Test` allows us to test our controllers in isolation. What are some of the methods it gives us to simulate the request/response cycle?
  - you can use the regular http verbs (get/put/post/delete) to make requests and then use things like .last_response to check and see if the right data is coming back
14. Describe some techniques to make our Sinatra views more DRY. Give an example of when you would use these techniques.
  - building logic out into partials, for example if you're repeating a form many times over the course of an application.
  - using a layout.erb file to build the basic structure for your views - if you've got a header or a navbar or even just an app-wide CSS file you could use a layout file to make sure each page loads the same styling


### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
  - .create - makes a thing, saves that thing
  - .pluck - finds a thing in a table by column names
  - .average - returns average value of column contents
  - .order - lets you specify the way returned results should be ordered
  - .limit - allows you to specify exactly how many records should be returned
2. Name your three favorite ActiveRecord rake tasks and describe what they do.
  - rake db:drop - blows up the database. scorched-earth. nothing's left. time to rebuild.
  - rake db:create - with a word we create... a database! (or more!)
  - rake db:migrate - sets everything up, makes changes, etc.
3. What's the difference between agile workflow and waterfall method?
  - see q# 6 above.
4. What can you expect from a group as you begin working together? As you continue working together?
  - awkwardness as you begin, maybe some "storming" or conflict. Eventually if all goes well: teamwork, success.
5. What two columns does `t.timestamps null: false` create in our database?
  - it creates created_at and updated_at columns
6. What cURL flag can you use to send a `POST` request?
  - curl -d
7. What case does JSON (and JavaScript) use for multi-word variables?
  - camel-case
8. What case does Ruby use for multi-word variables?
  - snake-case
9. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
  - schools will have_many teachers, teachers will belong_to schools.
10. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
    School - > has_many Teachers
    (id, name)
    Teacher - > belongs_to School
    (id, name, school_id)
11. Give an example of when you might want to store information besides ids on a join table.  
  you might want to store info besides ids on a join table if objects have other unique identifiers - SSN's, VINs, etc
12. Describe and diagram the relationship between patients and doctors.
  doctors - > has_many patients
  (id, name)
  patients - > belongs_to doctors
  (id, name, doctor_id)
13. Describe and diagram the relationship between museums and original_paintings.
  museums has_many - > original_paintings
  (name, id)
  original_paintings belongs_to -> museums
  (name, id, museum_id)
14. What are some examples of acceptable values for the parts of an HTTP response?
  status code - 200, 404, 500, 418 (that last one if you're pinging a tea pot)
  header - connection, cookie, user_agent
  body - "Hello World!" 
15. What types of output do we want to test when we test our controllers?
 - we want to find out if we're getting redirected to the right page, or being able to create + save data, or delete/edit - basically we're testing to make sure CRUD functionality exists.
16. What could you see in your code that would make you think you might want to create a partial?
 - continually repeated html blocks - often a form or something similar
17. Why might you use a helper method?
  - if you want access to a method in both controllers and views (I guess this is like if you want to be able to access a user across various views? Not sure.)
