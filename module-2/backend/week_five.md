Questions from Week 5:
1. How do we make flash messages display on a page?
  ```
   <% flash.each do |type, message| %>
     <%= content_tag :div message.html_safe, class: name %>
   <% end %>
  ```
2. Where is cart information/temporary information usually stored?
  session
3. What might be some reasons not to store a cart in our database? Are there any reasons why we would want to persist that information?
  We probably don't want to store a cart in our database most of the time because of constantly changing product information, and perhaps unnecessary data storage in the event that people forget their accounts or never check their carts out

  We might want to store a cart in our database if we had a user setup like Amazon, where we'd like a user's cart & wishlist items to persist until they've purchased an item or explicitly removed it.

4. What is the purpose of the asset pipeline?
  To help with asset management and organization & help sites serve assets more quickly and efficiently

5. Why do we precompile our assets?
   Speed & space

6. What do each of the following tags do?

```
<%= stylesheet_link_tag "application" %>
<%= javascript_include_tag "application" %>
<%= image_tag "rails.png" %>
```
  rails helper method for ```<link href="application.css" type="text/css" rel="stylesheet">```
  rails helper method for ```<script href="application.js" type="text/javascript">```
  rails helper method for ```<img src="assets/rails.png">```
 * important to note that these methods do more than the raw html tags in terms of asset management

7. What are some of the elements of a great read me? What are some of the benefits of taking the time to update a readme for our project?
  * clear summary of what an app does, clear instructions and examples demonstrating how to run the app and/or integrate it with other apps, tables of contents if they are very long readmes, links to external resources, references to common troubleshoots
  * tells people how to run our apps, also contextualizes our apps so potential collaborators and employers are aware of why we made an app and at what point in our careers as programmers

8. What are the top four accessibility issues that we as developers should be aware of?
  * Vision, hearing, mental ability & physical impairment

9. `before_save` is an example of a what? Where in our Rails application would we find a `before_save`?
  callback or filter, our model

10. Given the following object, how would we create a scope for all users who are active?

```ruby
User.create(name: "Happy", active: true)
```
scope active:, -> where(active:true)

11. What is the difference between a scope and a class method?
 I thought scope was just syntactical sugar for specific kinds of class methods, but further research shows that scopes make it easier to acount for certain edge cases like nil arguments that can prevent method chaining

Review Questions:  
12. Given the following hash:  

```ruby
{cart: {"17" => 4, "204" => 52, "29" => 22}}
```

  12a. How would you add item with id of 48 with a quantity of 4?  
  ``` hash[:cart]["48"] = 4 ```
  12b. How would you increase the quantity of item 29?  
  ``` hash[:cart]["29"] += 1 ```
  12c. How would you find out how many items your user is thinking about purchasing?   
  ``` hash[:cart].values.sum ```
13. What is polymorphism? How does it relate to duck-typing? What are two ways you use this in everyday Rails applications?
   Polymorphism is the ability of a single class or object to take many forms while generally preserving a public interface. This is related to duck typing in that it is the foundation of duck typing - a duck one class among many classes that can interface with another objects public interface without breaking (if it walks like a duck and talks like a duck then treat it like a duck)
14. How would you clean the string "(630) 854-5483" to "630.854.5483"?  
  string. a.delete("()").sub(" ", ".").sub("-", ".")
  or use regex
  a.delete("()").gsub(/[ -]/, ".")
