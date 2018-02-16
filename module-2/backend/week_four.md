## Week Four Recap

### Instructions
Fork this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

1. What is a cookie?
* A small piece of data stored in the browser to send stored information to the server with each request
2. What’s the difference between a session and a cookie?
* A session is a larger piece of data, generally designed to maintain state across stateless http requests, and where a cookie is always stored client side, sessions can be stored either server or client side.
3. What’s a flash and when do you want to use flashes?
* Flash is similar to a session in that it is designed to maintain state across requests, but is different in that it only maintains that state for one additional request.
4. Why do people say “HTTP is stateless”?
* Because each each request is completely independent & ignorant of other requests.
5. What’s authentication? Explain.
* Authentication is the process of verifying a vistor to a site is who they say they are. This process allows us to customize ux based on user id.
6. What’s the difference between authentication and authorization?
* Authentication is simply the process of visitor identification, where as authorization is the process of determining what user can access what views, controllers & models in each site.
7. What’s a before filter?
* A before filter is a method we call before a controller action is executed. We've seen them so far in the context of setting variables & preventing certain users from accessing certain controller actions.
8. How do we keep track of a user once they’ve logged in?
* Session data
9. When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?
* Namespacing resources has to with access organization & clarity in uris
* Nesting resources is used to establish more relationship oriented organization between models, i.e: specific companies having specific sets of jobs.
10. At a high level, what tools can you use to implement authorization? How would you use them?
* Namespacing
* User roles (as ENUMs)
11. What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?
* Enum is a built in rails helper that allows us to limit & index a model's attribute
12. What are some strategies you can use to keep your views DRY?
* partials
* layouts
* keeping logic in controllers
* creating class & instance methods in models


Reviews Questions
13. Given the following array of hashes, how would I print an alphabetical list of holidays?
```ruby
[
 {holiday: {name: "St Patrick's Day", supplies: ["Corned Beef and Cabbage"]}},
 {holiday: {name: "Halloween", supplies: ["Candy", "Costume"]}},
 {holiday: {name: "Hanukkah", supplies: ["Menorah"]}}
]
```  
```
abc_holiday_names = above_array.map {|holiday_hash| holiday_hash[:holiday][:name].downcase}.sort
abc_holiday_names.each do {|holiday_name| print holiday_name}
```
14. How would you clean incoming data to ensure "$300" or "300.00" is stored as 300?
```.delete("$").to_i ```
