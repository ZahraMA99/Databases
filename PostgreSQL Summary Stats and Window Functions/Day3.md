1. PARTITION BY
00:00 - 00:11
You now know how to change the behavior of a window function with the ORDER BY subclause. Another way to change its behavior is with the PARTITION BY subclause.

2. Motivation
00:11 - 00:40
Let's build on last video's example to see why partitioning is useful. In addition to discus throw champions, this query includes triple jump champions as well. However, when using LAG, the first Triple Jump's Last_Champion is GER, Discus Throw's most recent champion, when in fact it should be null, since the two events are different and their champions are not related. How do you tell LAG to separate the two events?

3. Enter PARTITION BY
00:40 - 01:11
Enter PARTITION BY. This OVER subclause splits the table into partitions based on a column's unique values, similar to GROUP BY. Unlike GROUP BY, however, the results of a window function with PARTITION BY aren't rolled into one column. Partitions are operated on separately by the window function. For example, ROW_NUMBER will reset to 1 for each partition's first row, and LAG will only fetch a row's previous value if its previous row is in the same partition.

4. Partitioning by one column
01:11 - 01:38
Let's use PARTITION BY to fix this query's results. Adding PARTITION BY Event in the OVER clause before ORDER will separate the table into two partitions, one for Discus Throw and one for Triple Jump, the two unique values in the Event column. The one difference in the results is that the first row of the Triple Jump champions correctly has null as Last Champion. That's because it's the first row in its partition.

5. More complex partitioning
01:38 - 01:53
Let's look at a more complex partitioning. This result is a row numbering of Chinese and Japanese gold medals awarded to women. The row numbering extends across countries and events, and the goal is to reset it per country and year.

6. Partitioning by multiple columns
01:53 - 02:20
Partitioning by year and country in ROW_NUMBER will achieve this. Each combination of the unique values of Year and Country will be a partition. 2008 - China is one partition; 2008 - Japan is another, 2012 - China is yet another, and so on. As you can see in the result, the row number resets to 1 for each partition. You can partition by multiple columns if your groups are spread across columns.

7. Let's practice!
02:20 - 02:35
ORDER BY and PARTITION BY are the two most common subclauses used in window functions. Now that you know both, practice using them in the following assignments to master the basics of window functions.

**LINK** https://rpubs.com/cliex159/PostgreSQLSummaryStatsandWindowFunctions
