1. Sliding windows
00:00 - 00:13
In addition to calculating aggregate and rank information, window functions can also be used to calculate information that changes with each subsequent row in a data set.

2. Sliding windows
00:13 - 00:48
These types of window functions are called sliding windows. Sliding windows are functions that perform calculations relative to the current row of a data set. You can use sliding windows to calculate a wide variety of information that aggregates one row at a time down your data set -- running totals, sums, counts, and averages in any order you need. A sliding window calculation can also be partitioned by one or more columns, just like a non-sliding window.

3. Sliding window keywords
00:48 - 01:54
A sliding window function contains specific functions within the OVER clause to specify the data you want to use in your calculations. The general syntax looks like this -- you use the phrase ROWS BETWEEN to indicate that you plan on slicing information in your window function for each row in the data set, and then you specify the starting and finishing point of the calculation. For the start and finish in your ROWS BETWEEN statement, you can specify a number of keywords as shown here. PRECEDING and FOLLOWING are used to specify the number of rows before, or after, the current row that you want to include in a calculation. UNBOUNDED PRECEDING and UNBOUNDED FOLLOWING tell SQL that you want to include every row since the beginning, or the end, of the data set in your calculations. Finally, CURRENT ROW tells SQL that you want to stop your calculation at the current row.

4. Sliding window example
01:54 - 02:39
For example, the sliding window in this query includes several key pieces of information in its calculation. It first states that the goal is to calculate a sum of goals scored when Manchester City played as the home team during the 2011/2012 season. It then tells you that you want to turn this calculation into a running total, ordered by the date of the match from oldest to most recent and calculated from the beginning of the data set to the current row. Your resulting data set looks like this, with a column calculating the total number of goals scored across the season, with a final total listed in the last row.

5. Sliding window frame
02:39 - 03:21
Using the PRECEDING statement, you also have the ability to calculate sliding windows with a more limited frame. For example, the query you see here is similar to the previous one, with a slightly modified sliding window. The phrase UNBOUNDED PRECEDING is replaced here with the phrase 1 PRECEDING, which calculates the sum of Manchester City's goals in the current and previous match. As you see in the data set here, the two rows in red are used to calculate the sum on the second row, and the two rows in green are used to calculate the sum on the third row.

6. Let's practice!
03:21 - 03:35
There are a wide variety of sliding windows you can use to calculate information in your query. Let's practice here with some examples based on what we've reviewed so far.

**LINK:** https://rpubs.com/cliex159/IntermediateSQL
