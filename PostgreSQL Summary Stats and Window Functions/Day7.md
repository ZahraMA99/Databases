1. Aggregate window functions
00:00 - 00:13
Welcome back! In Chapter 2, you learned about new window functions to fetch, rank, and page rows; in Chapter 3, you'll use aggregate functions you already know in a new context.

2. Source table
00:13 - 00:22
Let's set up the source table first. This query returns the count of gold medals Brazil earned in these five sets of Olympic games.

3. Aggregate functions
00:22 - 00:55
After wrapping the previous query in a CTE (represented by the three points), using the MAX and SUM aggregate functions on the Medals column returns the highest medals earned in a year (18) and the total sum of medals earned across those years (64), respectively. These are standard aggregate functions that you can use either over the entire table or with GROUP BY. What if you want to see the maximum medals earned so far, or calculate the cumulative sum of medals earned?

4. MAX Window function
00:55 - 01:54
You can use both MAX and SUM, as well as the other aggregate functions COUNT, MIN, and AVG, as window functions. In this case, using MAX on the Medals column and defining a window ordered by year in ascending order will show the max medals earned so far for each row. For example, in 1992, Brazil earned 13 medals. Since it's the first row, that's the max so far of medals earned. In the next set of games, those of 1996, only 5 medals were earned, so the max is still 13. In 2004, the games after the 1996 games, 18 medals were earned, which is higher than the previous max of 13, so the max becomes 18. In the next two subsequent games, 14 medals were earned, which is less than 18, so the max remains 18 to the end of the query.

5. SUM Window function
01:54 - 02:20
SUM can also be used as a window function. With the same window that was defined for MAX used for SUM, SUM calculates the cumulative sum, or running total, of the medals earned so far. The first cumulative sum is 13, because there's no previous value to sum up. The second is 18, the sum of the medals earned in 1992 - 13 - and 1996 - 5.

6. Partitioning with aggregate window functions
02:20 - 03:04
Just like any other window function, you can partition with aggregate functions. The source table is expanded to include a country column and Cuba's earned medals. In the left table, SUM is used without partitioning by country, so the cumulative sum does not reset per country. The value in the last row, 84, reflects the total medals earned for both Brazil and Cuba. In the right table, SUM is used with partitioning by country, so the cumulative sum resets once the country changes. The last row's value, 46, reflects only the total medals earned by Cuba, while the last row for Brazil represents its own total medals earned, 46.

7. Let's practice!
03:04 - 03:13
Now that you know how to use aggregate functions in a new context, practice using them in the following exercises.

**LINK** 
