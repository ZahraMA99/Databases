1. Correlated subqueries
00:00 - 00:13
Welcome back! You're making fantastic progress so far. Now that you've covered the basics of simple subqueries, let's learn how to construct correlated subqueries.

2. Correlated subquery
00:13 - 00:44
Correlated subqueries are a special kind of subquery that use values from the outer query in order to generate the final results. The subquery is re-executed each time a new row in the final data set is returned, in order to properly generate each new piece of information. Correlated subqueries are used for special types of calculations, such as advanced joining, filtering, and evaluating of data in the database.

3. A simple example
00:44 - 01:03
Let's walk through an example of one of these queries. In the previous chapter, you completed an exercise that answered the question, "Which match stages, where the stakes get higher in each stage, tend to have a higher than average number of goals scored?"

4. A simple example
01:03 - 01:21
You achieved this using 3 simple subqueries in the SELECT, FROM, and WHERE statements. However, the same output can also be produced with a correlated subquery. Let's focus on the subquery in the WHERE statement.

5. A correlated example
01:21 - 01:52
This query has only one difference -- instead of including a filter by season, the WHERE clause filters for data where the outer table's match stage, pulled from the subquery in FROM, is HIGHER than the overall average generated in the WHERE subquery. The entire WHERE statement is saying, in essence, "return stages where the values in the subquery are higher than the average."

6. A correlated example
01:52 - 02:06
Here are the results generated by this query. This may seem a bit complicated, but with a few more examples and a bit of practice, you will start to get the hang of how useful correlated subqueries can be.

7. Simple vs. correlated subqueries
02:06 - 03:05
Let's quickly walk through some key differences between simple and correlated subqueries. Simple subqueries can be used in extracting, structuring or filtering information, and can run independent of the main query. In contrast, a correlated subquery cannot be executed on its own because it's dependent on values in the main query. Additionally, a simple subquery is evaluated once in the entire statement. A correlated subquery is evaluated in loops -- once for each row generated by the data set. This means that adding correlated subqueries will slow down your query performance, since your query is recalculating information over and over. Be careful not to include too many correlated subqueries -- or your query may take a long time to run!

8. Correlated subqueries
03:05 - 03:42
Here's another, smaller example of a query in which you can use a correlated subquery. Let's answer the question, "What is the average number of goals scored in each country across all match seasons?" This is an an easy enough question, right? You simply join the match table to the country table on the country's id, and extract the country's name, take an average of the goals scored, and group the entire query by the country's name, yielding one row with an average value per country.

9. Correlated subqueries
03:42 - 04:27
A correlated subquery can be used here in lieu of a join. Take a look at the outer query first. The name of the country is selected from the country table, aliased as "c". The second column selected is a scalar subquery, selecting the average total goals scored across all seasons from the match table. You'll notice that the WHERE clause asks SQL to return values where the inner, match table's country_id column matches the c.id column in the outer query's country table. This way, the entire join is replaced, and the results are identical.

10. Let's practice!
04:27 - 04:35
Okay! It's time to practice using correlated subqueries.

**LINK:** https://rpubs.com/cliex159/IntermediateSQL