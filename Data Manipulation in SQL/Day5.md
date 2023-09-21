1. Subqueries in the FROM statement
00:00 - 00:13
Fantastic! You're really getting the hang of using subqueries. In this lesson, we will cover the use of subqueries in your FROM statement.

2. Subqueries in FROM
00:13 - 01:37
You probably noticed that subqueries in WHERE can only return a single column. But what if you want to return a more complex set of results? Subqueries in the FROM statement are a robust tool for restructuring and transforming your data. Often, the data you need to answer a question is not yet in the format necessary to query it directly, and requires some additional processing to prepare for analysis. For example, you may want to transform your data into a different shape, or pre-filter it before making calculations. Subqueries in a FROM statement are a common way of preparing that data. Subqueries in FROM are also useful when calculating aggregates of aggregate information. Let's say you're interested in getting the top 3 teams who scored the highest number of home_goals on average in the 2011/2012 season. You would first calculate the average for each team in the league, and THEN calculate the max value for any team overall. This can be easily accomplished with a subquery in FROM.

3. FROM subqueries...
01:37 - 02:23
Let's examine the home_goal average for every team in the database. First, you will create the query that will become your subquery. This query here selects the team's long name from the "team" table, and the AVG of home_goal column from the "match" table. The team table is left joined onto the "match" table using hometeam_id, which will give you the identity of the home team. The query is then filtered by season and grouped by team. The results look like this -- an average value calculated for each team in the table.

4. ...to main queries!
02:23 - 02:37
In order to get only the top team as a final result, place this ENTIRE query without the semicolon inside the FROM statement of an outer query,

5. ...to main queries!
02:37 - 02:40
...make sure to give it an alias...

6. ...to main queries!
02:40 - 02:53
...then add it to the main query, selecting the team, and home_avg columns from the subquery, just as you would with any other table in the database.

7. ...to main queries!
02:53 - 03:16
Finally, don't forget to order by home_avg, descending, and limit the query to 3 results. The final query returns your top 3 teams based on home_goals scored in the 2011/2012 season. And it seems our top team for that season is Barcelona!

8. Things to remember
03:16 - 04:05
There are a few key things to remember when using subqueries in the FROM statement. The first, is that you have the ability to create more than one subquery in the FROM statement of any main query. When you do so, make sure that you give each subquery an alias, and make sure that you are able to JOIN them to each other, just as you would when querying a table from your database. Second, you can join a subquery to any existing table in your database. Again, however, you need to make sure you have a column in the subquery that you can use with the JOIN you'd like to perform.

9. Let's practice!
04:05 - 04:14
Fantastic! It's time for you to practice using subqueries in the FROM clause.

**Ex. LINK:** https://rpubs.com/cliex159/IntermediateSQL
