## Week Two - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!).

Note: When you're done, submit a PR.

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
* ActiveRecord is a framework to query SQL databases from ruby & rails applications.

2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?
* ActiveRecord automatically generates attributes for models based on their corresponding migrations, so #all, #find, #find_by, #pluck, #first, #last are some query class methods that come with this inheritance, as well as any column names for any instances of the Team class.

3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?
``` ruby
 team_4 = Team.find(4)
 team_4_owner = team_4.owner_id
 Owner.find(team_4_owner)
 ```

4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?
```ruby
team_4.owner
```

5. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.
* many-to-many
* students & teachers each with ids as keys + a student_teacher joins table with student_id & teacher_id as foreign keys in each record

6. Define foreign key, primary key, and schema.
* Foriegn key is a primary key of another table used so a record can reference that table
* Primary key is a unique identifying key associated with each tables record
* Schema is essentially a map of the database and its relations as they currently exist

7. Describe the relationship between a foreign key on one table and a primary key on another table.
* A foriegn key is the primary key of another table

8. What are the parts of an HTTP response?
* Headers (status_code + more information about the server) & Body (html, css, js)

### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
 * find_by - returns first record that matches condition, can be used for any attribute, where find is only for id
 * where - returns all records that match conditions, I like because most of the time i'm looking for record I don't just want the first match
 * average - averages numerical record values, very convenient
 * pluck - returns all values from a single column in a table, useful if you want to "zoom in" on a table's data
 * reverse_order - just like order, but it defaults to DESC instead of ASC, I think its cool active record included this method to improve code readability

2. Name your three favorite ActiveRecord rake tasks and describe what they do.
* rake db:test:setup - keeps your test tables up to date with development tables, very necessary for tdd
* rake db:create_migration NAME=AddColumn, very useful since tables seem to grow with projects
* rake db:create_migration NAME=RemoveColumn, very useful since sometimes unnecessary data is placed into tables

3. What two columns does `t.timestamps null: false` create in our database?
* Created_at & updated_at

4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
* one to many school to teachers

5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
* git teachers a school_id foreign key

6. Give an example of when you might want to store information besides ids on a join table.
* doctor patient join table might have columns for things like reason for visit, follow up, paid, etc

7. Describe and diagram the relationship between patients and doctors.
* patients have many doctors and doctors have many patients
* correlate the two with a join table containing the ids of each as foriegn keys

8. Describe and diagram the relationship between museums and original_paintings.
* museums always have many paintings, but paintings generally belong to only one museum, so giving a painting record a home_museum_id foriegn key would allow the painting to "belong to" a particular museum

9. What could you see in your code that would make you think you might want to create a partial?
* contact info footer
* nav bar
* forms & logins/logouts
