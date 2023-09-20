1. CASE WHEN with aggregate functions
00:00 - 00:08
Great job so far! Let's take a look at CASE statements with aggregate functions.

2. In CASE you need to aggregate
00:08 - 00:24
CASE statements can be used to create columns for categorizing data, and to filter your data in the WHERE clause. You can also use CASE statements to aggregate data based on the result of a logical test.

3. COUNTing CASES
00:24 - 00:48
Let's say you wanted to prepare a summary table counting the number of home and away games that Liverpool won in each season. If you've created summary tables in Spreadsheets, you can probably visualize the final table, here -- but how do you get a count of Liverpool's wins in each season?

4. CASE WHEN with COUNT
00:48 - 01:38
You guessed it -- a CASE statement. CASE statements are like any other column in your query, so you can include them inside an aggregate function. Take a look at the CASE statement. The WHEN clause includes a similar logical test to the previous lesson -- did Liverpool play as the home team, AND did the home team score higher than the away team? The difference begins in your THEN clause. Instead of returning a string of text, you return the column identifying the unique match id. When this CASE statement is inside the COUNT function, it COUNTS every id returned by this CASE statement.

5. CASE WHEN with COUNT
01:38 - 01:53
You then add a second CASE statement for the away team, and group the query by the season. When counting information in a CASE statement, you can return anything you'd like --

6. CASE WHEN with COUNT
01:53 - 02:05
a number, a string of text, or any column in the table, SQL is COUNTing the number of rows returned by the CASE statement.

7. CASE WHEN with SUM
02:05 - 02:41
Similarly, you can use the SUM function to calculate a total of any value. Let's say we're interested in the number of home and away goals that Liverpool scored in each season. This is fairly simple to set up -- if the hometeam_id is Liverpool's, return the home_goal value. The ELSE condition is assumed to be NULL, so the query returns the total home_goals scored by Liverpool in each season.

8. The CASE is fairly AVG...
02:41 - 03:11
You can also use the AVG function with CASE in two key ways. First, you can calculate an average of data. You can do this using CASE in the EXACT same way you used the SUM function. Just change out SUM for AVG in this query, and you instead get the AVG goals Liverpool scored in each season.

9. A ROUNDed AVG
03:11 - 03:23
You can make the results easier to read using ROUND. ROUND takes 2 arguments -- a numerical value, and the number of decimal points to round the value to.

10. A ROUNDed AVG
03:23 - 03:35
Place it outside your aggregate CASE statement, and include the number of decimal points at the end. There, that's much easier to read!

11. Percentages with CASE and AVG
03:35 - 04:36
The second key application of CASE with AVG is in the calculation of percentages. This requires a specific structure in order for your calculation to be accurate. The question we're answering here is, "What percentage of Liverpool's games did they win in each season?" The first component of this CASE statement is a WHEN clause identifying what you're calculating a percentage of -- in this case, how many games did they win? This is tested in the same way as previous slides, and your THEN clause returns a 1. The second component identifies Liverpool's games that they LOST, and returns the value 0. All other matches -- ties, games not involving Liverpool -- are excluded as NULLs. Here are the results of this query ...

12. Percentages with CASE and AVG
04:36 - 04:41
... and here's the ROUNDed, more readable version of the results.

13. Let's practice!
04:41 - 04:51
Now it's your turn to practice creating CASE statements with aggregate functions.

**link**: https://medium.com/艾蜜莉讀讀寫寫/datacamp-functions-for-manipulating-data-in-sql-server-a46a24bc1d6f
