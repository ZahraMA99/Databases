1. Nested subqueries
00:00 - 00:08
Building on the previous lesson, another important type of subquery to learn is the nested subquery.

2. Nested subqueries?
00:08 - 00:36
Nested subqueries are exactly as they sound -- subqueries nested inside other subqueries. As you saw in the previous chapter, information in a database is often not in the format you need to answer a question. Some types of questions you answer may require multiple layers of transformation and filtering of data before you extracting it into the main query.

3. A subquery...
00:36 - 01:01
Let's start with an example. The query you see here is similar to a previous lesson where we selected the average number of goals scored in a match within each country, and compared it to the overall average using a subquery in SELECT. This third column calculates the difference between each country, and the overall average.

4. A subquery...
01:01 - 01:09
The resulting table looks like this, with one row for each country, and one column for each of the two calculations.

5. ...inside a subquery!
01:09 - 01:32
Let's answer a similar question with an additional layer -- How does each month's total goals differ from the monthly average of goals scored? The query here, similar to the previous one, answers this question. Let's take some time to walk through the necessary steps to get this result.

6. Inner subquery
01:32 - 01:56
The subquery logic reads like this -- first, select the sum of goals scored in each month. The month is queried using the EXTRACT function, FROM the date. Here are the results of that first, inner subquery, which includes results for months 1 through 12.

7. Outer subquery
01:56 - 02:21
Next, you can place the subquery into the second, outer subquery to calculate an average of the values generated in the previous table, giving you the average monthly goals scored. Since this result is a scalar subquery, you can now place it in the main query for calculating the final data set.

8. Final query
02:21 - 02:47
Finally, you can place the entire nested subquery in the SELECT statement, giving you a scalar value to compare to the SUM of goals scored in each month. Here are the first 4 rows of the final query, which generates a sum of goals scored in the month, and a column subtracting the goals scored, from the overall monthly average.

9. Correlated nested subqueries
02:47 - 03:17
It's important to also note that nested queries can be correlated or uncorrelated. They can also be a combination of the two -- the inner subquery can be correlated, the outer uncorrelated, or vice versa! And each of the correlated subqueries can reference information from an outer subquery, or the main query. It entirely depends on the problem you're looking to solve. Let's look at an example.

10. Correlated nested subqueries
03:17 - 03:35
Let's look at another example here. This query answers the question, What is each country's average goals scored in a match in the 2011/2012 season? This is fairly similar to the previous chapter, except it takes one additional step.

11. Correlated nested subqueries
03:35 - 03:40
It has a second, nested subquery inside the SELECT statement,

12. Correlated nested subquery
03:40 - 03:47
and the outer subquery has a statement correlating with the main query.

13. Correlated nested subqueries
03:47 - 03:57
The result you see here is a table with a column that identifies each country's average goals scored in the 2011/2012 season.

14. Let's practice!
03:57 - 04:06
Okay! Let's practice creating some nested subqueries.

**LINK:** https://rpubs.com/cliex159/IntermediateSQL
