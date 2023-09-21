1. Ranking
00:00 - 00:10
Another common application of window functions is ranking rows according to their values. Let's learn about the three ranking functions in this video.

2. The ranking functions
00:10 - 00:59
You've already encountered one ranking function last chapter: ROW_NUMBER. Assigning numbers to rows is one way of ranking them. ROW_NUMBER always assigns unique numbers, even if two rows' values are the same; it chooses some other metric to assign numbers if the value by which it's ordering is the same. Another ranking function is RANK. It assigns the same number to rows with identical values, skipping over the next numbers in such cases. Finally, DENSE_RANK also assigns the same number to rows with identical values, but doesn't skip over the next numbers. This sounds a bit abstract, so let's see all three functions used at once to distinguish between their outputs.

3. Source table
00:59 - 01:19
This query returns the number of Olympic games in which each of these countries has participated. Notice that some countries, such as France and Denmark, have participated in the same number of games. How would you rank them? Let's apply the three ranking functions to see how each handles these repeated values.

4. Different ranking functions - ROW_NUMBER
01:19 - 01:42
After wrapping the previous query in a CTE and applying the three ranking functions to them, let's see the differences in the output. ROW_NUMBER's output is familiar; it assigns a unique number to each row based on the provided order. If two rows have the same value, it still assigns them unique numbers, but based on an internally selected order.

5. Different ranking functions - RANK
01:42 - 02:03
RANK will assign the same number to two rows if their values are equal; both Denmark and France are second here. After the repeated ranks, it skips over the next rank, and immediately goes to four for Italy. RANK always skips over the next numbers if it assigns the same number to two or more rows.

6. Different ranking functions - DENSE_RANK
02:03 - 02:25
DENSE_RANK also assigns 2 to Denmark and France, but instead of skipping the next rank, it assigns 3 to Italy. DENSE_RANK never skips ranks. ROW_NUMBER and RANK will have the same last rank, the count of rows, while DENSE_RANK's last rank is the count of unique values being ranked.

7. Ranking without partitioning - Source table
02:25 - 02:42
What if you have several groups you need to rank separately in your data? This query returns two groups of athletes from China and Russia that need to be ranked by how many medals they've earned. Let's see what happens when you rank them without partitioning.

8. Ranking without partitioning
02:42 - 03:04
The two groups of athletes are ranked here without partitioning. Because of the ORDER BY clause at the end of the query, the results are ordered correctly, but notice that the Russian athletes who won 2 medals each are ranked third, when they should be ranked second. That's because they're ranked relative to the entire table, not to the Russian group of athletes.

9. Ranking with partitioning
03:04 - 03:24
After partitioning by country, the Russian athletes are correctly assigned the second rank because they're being ranked only relative to the other athletes in their group or partition. If you have more than one group whose rows you want to rank, make sure to partition by the column that splits your rows into the correct groups.

10. Let's practice!
03:24 - 03:32
Practice ranking rows with the different ranking functions in the following exercises.

**LINK** https://rpubs.com/cliex159/PostgreSQLSummaryStatsandWindowFunctions
