1. Subqueries in SELECT
00:00 - 00:16
So far, we've covered the use of simple subqueries in FROM and WHERE statements. Subqueries can also be included in a SELECT statement to bring summary values into a detailed data set.

2. SELECTing what?
00:16 - 00:57
Subqueries in SELECT are used to return a single, aggregate value. This can be fairly useful, since, as you'll recall, you cannot include an aggregate value in an ungrouped SQL query. Subqueries in SELECT are one way to get around that. Subqieries in SELECT are also useful when performing complex mathematical calculations on information in your data set. For example, you may want to see how much an individual score deviates from an average -- say, how higher than the average is this individual score?

3. Subqueries in SELECT
00:57 - 01:30
Including a subquery in SELECT is fairly simple, and is set up the same way you set up subqueries in the WHERE and FROM clauses. Let's say we want to create a column to compare the total number of matches played in each season to the total number of matches played OVERALL. We can first calculate the overall count of matches across all seasons, which is 12,837.

4. Subqueries in SELECT
01:30 - 01:36
We can then add that single number to the SELECT statement, which yields the following results...

5. Subqueries in SELECT
01:36 - 01:45
...or, we can skip that step, and add the subquery directly to the SELECT statement to get identical results.

6. SELECT subqueries for mathematical calculations
01:45 - 02:28
Subqueries in SELECT are also incredibly useful for calculations with the data you are querying. The single value returned by a subquery in select can be used to calculate information based on existing information in a database. For example, the overall average number of goals scored in a match across all seasons is 2.72. If you want to calculate the difference from the average in any given match, you can either calculate this number ahead of time in a separate query, and input the value into the SELECT statement...

7. Subqueries in SELECT
02:28 - 02:52
...or you can use a subquery that calculates this value for you in your SELECT statement, and subtract it from the total goals in that match. Overall, this second option can save you a lot of time and errors in your work, and the results you see here, are identical to calculating the result manually.

8. SELECT subqueries -- things to keep in mind
02:52 - 04:02
There are a few unique considerations when working with subqueries in SELECT. The first is that the subquery needs to return a single value. If your subquery result returns multiple rows, your entire query will generate an error. This is because the information retrieved in a SELECT query is applied identically to each row in the data set -- and that's not possible if there's more than one unit of information. The second thing to keep an eye out is the correct placement of your data's filters in both the main query and the subquery. Here is the query from the previous slide. Since the subquery is processed before the main query, you'll need to include relevant filters in the subquery as well as the main query. Without the WHERE clause you see here in the subquery, the number returned would have been the overall average across all seasons rather than in the 2011/2012 season.

9. Let's practice!
04:02 - 04:12
Okay! Let's practice a few examples of subqueries in the SELECT statement.

**LINK:** 
