1. WHERE are the subqueries?
00:00 - 00:12
Welcome back! In this chapter, we will cover the use of simple subqueries to extract and transform your data.

2. What is a subquery?
00:12 - 00:53
A subquery is a query nested inside another query. You can tell that there is a subquery in your SQL statement if you have an additional SELECT statement contained inside parentheses, surrounded by another complete SQL statement. So why is this important? Often, in order to retrieve information you want, you have to perform some intermediary transformations to your data before selecting, filtering, or calculating information. Subqueries are a common way of performing this transformation.

3. What do you do with subqueries?
00:53 - 01:31
A subquery can be placed in any part of your query -- such as the SELECT, FROM, WHERE, or GROUP BY clause. Where you place it depends on what you want your final data to look like. A subquery can return a variety of information, such as scalar quantities, or numbers, like the ones listed here. A subquery can return a list to use for filtering or joining information, or it can return a table to extract and further transform data.

4. Why subqueries?
01:31 - 02:21
So why might you need to use a subquery? Subqueries allow you to compare summarized values to detailed data. For example, compare Liverpool's performance to the entire English Premier League. Subqueries also allow you to better structure or reshape your data for multiple purposes, such as determining the highest monthly average of goals scored in the Bundesliga. Finally, subqueries allow you to combine data from tables where you are unable to perform a join, such as getting both the home and away team names into your results table. We'll discuss all of these questions in the coming lessons.

5. Simple subqueries
02:21 - 02:50
Let's start with the definition of a simple subquery. A simple subquery is a query, nested inside another query, that can be run on its own. The example you see here has a subquery in the WHERE clause -- if you copy the entire inner query, "SELECT the average home goal FROM the match table", you can run it on its own and get a result.

6. Simple subqueries
02:50 - 03:30
A simple subquery is also evaluated once in the entire query. This means that SQL first processes the information inside the subquery, gets the information it needs, and then moves on to processing information in the OUTER query. Here is the same query you see above. The subquery in WHERE is processed first, generating the overall average of home goals scored. SQL then moves onto the main query, treating the subquery like the single, aggregate value it just generated.

7. Subqueries in the WHERE clause
03:30 - 04:01
The first type of simple subquery we'll explore is the subquery in the WHERE clause. These are useful for filtering results based on information you'd have to calculate separately beforehand. Let's generate a list of matches in the 2012/2013 season where the number of home goals scored was higher than overall average. You could calculate the average, and then include that number in the main query...

8. Subqueries in the WHERE clause
04:01 - 04:16
...or you could put the query directly into the WHERE clause, inside parentheses. This way, you have one less manual step to perform before getting the results you need.

9. Subquery filtering list with IN
04:16 - 04:54
Subqueries are also useful for generating a filtering list. This query answers the question, "Which teams are part of Poland's league?" The "team" table doesn't have the country IDs, but the "match" table has both country and team IDs. By querying a list of hometeam_id's from match where the country_id is 15722, which indicates "Poland", you can generate a list to compare to the team_api_id column IN the WHERE clause.

10. Practice time!
04:54 - 05:02
Great! Let's practice creating simple subqueries in the WHERE clause.

**LINK**: https://rpubs.com/cliex159/IntermediateSQL
