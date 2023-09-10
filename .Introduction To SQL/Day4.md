##  Introducing queries :jack_o_lantern:
Now that we understand how data is organized in databases, we can begin drawing insights using SQL queries!

## Keywords :frog:
**Keywords are reserved words used to indicate what operation we'd like our code to perform.**
- The two most common keywords are SELECT and FROM. 
1. The SELECT keyword indicates which fields should be selected - in this case, the name field.
2. The FROM keyword indicates the table in which these fields are located - in this case, the patrons table.

## Our first query :crystal_ball:
- Here's how the query should be written. The SELECT statement appears first, followed on the next line by the FROM statement.
- It's best practice to end the query with a semicolon to indicate that the query is complete.
- We also capitalize keywords while keeping table and field names all lowercase.
- Now let's take a look at the results of our query, often called a result set.
- The result set lists all patron names, just as we had hoped. Note that we have not changed our database by writing this query.
- The tables, including the patrons table, are exactly the same as before we wrote the query. I
- n order to share our results, we can save the SQL code we have written so that our collaborators can use it to query the database themselves.
- We'll cover saving queries in a later lesson.

## Selecting multiple fields :earth_africa:
**To select multiple fields, we can list multiple field names after the SELECT keyword, separated by commas.**
- For example, to select card number and name, we'd list both field names in the order we'd like them to appear in our result set.
- Notice that this does not have to match the order the fields are presented in the table: listing name before card_num means that name appears first in the results.

## Selecting multiple fields :mushroom:
- As you might expect, we can select three fields such as name, card_num, and total_fine by listing all three field names after the SELECT keyword and separating them with commas.

## Selecting all fields :ear_of_rice:
- What if we'd like to select all four fields in the patrons table? We could list out the four field names after the SELECT statement,
- but there's an even easier way: we can tell SQL to select all fields using an asterisk (*) in place of the four field names.
