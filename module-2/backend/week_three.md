## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

1. What is the entry at the command line to create a new rails app?
* rails new appname (-T for no minitest, -d="desireddatabase", --skip-turbolinks --skip-spring for us so far)
2. What do Models generally inherit from in rails?
* ApplicationRecord
3. What do Controllers generally inherit from in a rails project?
* ApplicationController
4. How would I create a route if I wanted to see a specific horse in my routes file assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?
* get "/horses/:id", to: "horses#show"
5. What rake task is useful when looking at routes, and what information does it give you?
* rake routes
6. What is an example of a route helper? When would you use them?
* horses_path, instead of "/horses", generally useful instead of interpolating into strings
7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?
* url is whole url, path is just the uri appended to the main domain
8. What are strong params and why are they necessary?
* strong params are a set of parameters that the programmer explicitly allows to be used within the controller, they are necessary to filter out unwanted parameters injected by potentially unwelcome visitors
9. What role does `form_for` play in helping us create our forms?
* it acts as a convienient & smart alias for the html form tag, allows us to associate the data being passed from form to controller more efficiently
10. How does `form_for` know where to submit the user's input?
* the parameter you give it (i.e. ```form_for @user do |f|```)
11. Create a form using a `form_for` helper to create a new `Horse`.
*
```<%= form_for @horse do |f| %>
     <%= f.label :name %>
     <%= f.text_field :name %>

     <%= f.submit %>
   <% end %>
```
12. Why do we want to validate our models?
* to help keep data relatively clean, i.e. so users can't just make a bunch of the same record, or a bunch of empty records, etc
