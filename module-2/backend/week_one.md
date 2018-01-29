## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.
* GET - fetch resource
* POST - create new resource
* PUT - update entire resource
* PATCH - update partial resource
* DELETE - delete resource
2. What is Sinatra?
* A lightweight ruby framework
4. What is MVC?
* Model View Controller, a way of structuring internal server calls
5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
* Because sinatra depends on these conventions when looking up files and it makes our code easier to read
6. What types of variables are accessible in our view templates without explicitly passing them?
* instance variables but locals can be called if they are explicitly passed to the view from the controller
7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?
  ```ruby
  get '/horses' do
    @count = 1
    erb :index
  end
  ```

8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?
  ```ruby
  get '/horses' do
    erb :index, :locals => {:name => "Mr. Ed"}
  end
  ```

9. What's the purpose of ERB?
* To allow us to call ruby attributes and behaviors in html formats

10. Why do I need a development AND test database?
* Development database is so we can work with our programs in a near-full-scale setting
* Test database so we don't have to work with large datasets when testing models and features

11. What is CRUD and why is it important?
* Create Read Update Destroy
* It's important because it allows us to transfer data in a RESTful way and avoid unnecessary duplications

12. What does HTTP stand for?
* HyperText Transfer Protocol

13. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
* <% %> and <%= %>, the first is to interpolate Ruby without rendering the view, the second is to interpolate Ruby so it does render in the view

14. What's an ORM?
* Object Relational Mapping, converts data into virtual database so a particular OO language can interact with it

15. What's the most commonly used ORM in ruby (Sinatra & Rails)?
* ActiveRecord

16. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
* GET "/"
* GET "/menu"
* GET "/menu/new"
* POST "/menu"
* GET "/menu/update"
* PATCH "/menu"
* DELETE "/menu"

17. What's a migration?
* A migration is a set of instructions for creating a database

18. When you create a migration, does it automatically modify your database?
* No, you have to run a migration to affect your database

19. How does a model relate to a database?
* A model represents table data with objects and manipulates those objects

20. What is the difference between `#new` and `#create`?
* #new makes a new object that must be saved to be put into the database
* #create is a combination of #new and #save

### Review Questions:  
21. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film?
```
films = CSV.open("/films.csv", headers: true, header_converters: true)
films.each do |film|
  Film.create(id: film[:id],
           title: film[:title],
           description: film[:description])
end
```

22. Given the following hash:
```
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone'],
  brunch: {cost: $35, supplies: ['mimosa flutes'],
  antiquing: {cost: $200, supplies: ['list of antique stores']
}
```
How would I add 'granola bar' to things you should have when hiking?
```
activities[:hiking][:supplies].push('granola bar')
```
23. What are the 4 Principles of OOP? Give a one sentence explanation of each.
* Encapsulation - hides data so that objects only know about what they need to know
* Abstraction - allows objects to be used without knowing exactly what is going on inside the objects
* Inheritance - classes derived from others will inherit their behavoir
* Polymorphism - one method can occur in different places - if a subclass has a method of the same name as its superclass that method is demonstrating overriding polymorphism because that method overrides the method of the same name in its super class. The other kind of polymorphism is overloading, which would be giving one class various definitions of a method of the same name, leaving Ruby to figure out which method fits the scenario based on the data it is passed.

### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
