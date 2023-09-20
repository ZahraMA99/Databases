1. Subqueries inside FROM
00:00 - 00:08
The last type of subquery we'll cover is a query inside a FROM clause. Let's dig in!

2. Subqueries inside FROM
00:08 - 00:41
Let's say we are interested in all the continents with monarchs, along with the most recent country to gain independence in that continent. A starting SQL query to pull all the most recent independence years by continent is shown. The query groups records by continent and returns the most recent independence year for each group, by using the MAX() function AS most_recent. The result set is shown. Now how do we filter this for continents with monarchs?

3. Focusing on records inside monarchs
00:41 - 01:14
We haven't seen yet that we can include multiple tables in a FROM clause by adding a comma between them. In the SQL syntax shown, we include two different tables, left_table and right_table, in our FROM clause. The diagram shown illustrates that this query returns duplicates for multiple occurrences of id when it matches in both tables. We can drop duplicates using the DISTINCT command in the query shown. Let's investigate a way to solve our problem using this trick.

4. Finishing off the subquery
01:14 - 02:14
We can nest the subquery we initially wrote into a FROM statement, so that we are selecting from both monarchs and our subquery, aliased as "sub". We also use the WHERE clause as before to identify records in both tables that match on continent. As we saw on the previous slide, because the continents from our subquery will find multiple matches in monarchs, this match will return duplicates. As before, in our SELECT statement, we use the DISTINCT command to drop duplicate continents, and select sub-dot-most_recent to get the most recent independence year for each continent. Lastly, we ORDER BY continent. Have a look at our result set. There we have it: the continents with monarchs in our database, and the most recent year of independence in those continents! That's how we include a subquery as a temporary table in our FROM clause and then SELECT from it.

5. Let's practice!
02:14 - 02:31
We are very close to the end of the course. Awesome work on making it this far! The remaining exercises are designed to be challenging as they put together many of the topics we've learned so far. Stick with it!

**LINK:** https://iqraanwar.medium.com/10-subqueries-aa0f8310ce38
