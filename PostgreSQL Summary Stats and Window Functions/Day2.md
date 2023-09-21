1. ORDER BY
00:00 - 00:11
In the previous video, you learned the basics of a window function. In this video, you'll learn about ORDER BY, one of the subclauses within the OVER clause.

2. Row numbers
00:11 - 00:32
Recall the row numbering query from the last video. The first row's number is 1, the second is 2, and so on. What if you want to reverse the numbers? In other words, you want to assign 1 to the last row, 2 to the row before last, and so on.

3. Enter ORDER BY
00:32 - 00:57
Enter ORDER BY. ORDER BY is a subclause of OVER. It orders the rows related to the current row that the window function will use. Taking the row numbering query, if you order by year in descending order within the OVER clause, the function will assign 1 to the first row in that window. That row will have the most recent year in the dataset.

4. Ordering by Year in descending order
00:57 - 01:10
This is the result. Adding ORDER BY within OVER changed the basis on which the function assigned numbers to rows, assigning lower numbers to the more recent rows.

5. Ordering by multiple columns
01:10 - 01:35
In the previous results, notice that the results and numbers are only based on a sort by year. What if you want to sort by year and by event? You can order by multiple columns in the OVER clause, just like you normally can outside of it. That'll also change the numbers assigned to each row, since their positions have changed.

6. Ordering in- and outside OVER
01:35 - 02:27
You can ORDER both inside and outside OVER at the same time. In this query, row numbers are assigned based on the year and the event, but the ordering outside OVER orders by country and row. How will these two orders be executed? First, ROW_NUMBER will assign numbers based on the order within OVER. So the row numbers are given after sorting the table by year and event. After that, the ORDER outside of OVER takes over, and sorts the results of the table by Country and row number. Notice that the first row in the result isn't the row with number 1, because the two orders are based on different columns. From that, you can conclude that the ORDER inside OVER takes effect before the ORDER outside of it.

7. Reigning champion
02:27 - 03:07
One of the applications of window functions is determining reigning champion status. A reigning champion is a champion who's won both the previous and current years' competitions. To determine if a champion is a reigning champion, the previous and the current years' champions need to be in the same row, in two different columns, so that they can be compared. How can you get a previous row's value without complex self-joins? Enter LAG. LAG is a window function that takes a column and a number n and returns the column's value n rows before the current row. Passing 1 as n returns the previous row's value.

8. Current champions
03:07 - 03:17
This query returns the Discus Throw champions. Getting each year's champion is the first step to using LAG to get each year's previous champion.

9. Current and last champions
03:17 - 03:51
After wrapping the previous query in a CTE, which is a way to temporarily store a query's results as a table, select the year and champion, and use LAG on the Champion column with an n of 1, ordering by year in ascending order in OVER. In the results, notice that Last_Champion contains Champion's value from the previous row. The first row has no previous row, so its value is null.

10. Let's practice!
00:00 - 03:51
Now that you know the ins and outs of the ORDER BY subclause, let's practice using it in the following exercises.

**LINK** https://rpubs.com/cliex159/PostgreSQLSummaryStatsandWindowFunctions
