1. Window Functions
00:00 - 00:12
Great job! You now have experience transforming data using simple subqueries, correlated subqueries, and common table expressions.

2. Working with aggregate values
00:12 - 00:36
Let's tackle another limitation you've likely encountered in SQL -- the fact that you have to group results when using aggregate functions. If you try to retrieve additional information without grouping by every single non-aggregate value, your query will return an error. Thus, you can't compare aggregate values to non-aggregate data.

3. Introducing window functions!
00:36 - 01:12
You can work around this limitation using a window function. Window functions are a class of functions that perform calculations on a result set that has already been generated, also referred to as a "window". You can use window functions to perform aggregate calculations without having to group your data, just as you did with a subquery in SELECT. You can also use them to calculate information such as running totals, rankings, and moving averages.

4. What's a window function?
01:12 - 01:40
So what's a window function? How do you use it? Let's start with a query from chapter 2, where we answered the question, "how many goals were scored in each match in 2011/2012, and how did that compare to the average?" This query selects two columns from match table, and then used a subquery in SELECT to pass the overall average along the data set without aggregating the results.

5. What's a window function?
01:40 - 02:15
The same results can be generated using the clause common to all window functions -- the OVER clause. Instead of writing a subquery, calculate the AVG of home_goal and away_goal, and follow it with the OVER clause. This clause tells SQL to "pass this aggregate value over this existing result set." The results are identical to the previous statement that used a subquery in SELECT, with a simpler syntax and faster processing time.

6. Generate a RANK
02:15 - 02:46
Another simple type of column you can generate with a window function is a RANK. A RANK simply creates a column numbering your data set from highest to lowest, or lowest to highest, based on a column that you specify. Let's take the same query as the previous example, without the window function, and use it to answer the question -- what is the RANK of matches based on the number of goals scored?

7. Generate a RANK
02:46 - 03:27
We can answer this using the RANK window function. In order to set this up, let's add a new column in SELECT as you see here. To create the rank, you start with the RANK function, using parentheses, followed by the OVER clause. Inside the OVER clause, include the ORDER BY clause, and the column or columns you want to use to generate the rank. By default, the RANK function orders the results and ranking from smallest to largest values. In the case of our data set here, this isn't particularly informative.

8. Generate a RANK
03:27 - 03:51
You can easily correct this by adding the DESC function to reverse the order of the rank, just as you would if you were using ORDER BY at the end of your query. You'll notice that the RANK function automatically ties identical values, such as the first 2 results, and then skips the next value in the rank.

9. Key differences
03:51 - 04:26
There are a few key considerations when using window functions. First, window functions are processed after the entire query except the final ORDER BY statement. Thus, the window function uses the result set to calculate information, as opposed to using the database directly. Second, it's important to know that window functions are available in PostgreSQL, Oracle, MySQL, but not in SQLite.

10. Let's practice!
04:26 - 04:34
Okay, let's practice some simple window functions using the OVER clause!

link: 
