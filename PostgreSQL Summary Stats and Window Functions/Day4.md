1. Fetching
00:00 - 00:14
Welcome back! You learned the basics of window functions in Chapter 1; in Chapter 2, you'll learn some practical applications. In this video, you'll learn how to fetch values from different parts of the table into one row.

2. The four functions
00:14 - 01:00
You've already encountered the fetching function LAG, which returns the value at n rows before the current row. LEAD is much the same, except it returns the value at n rows AFTER the current row. These two functions are relative fetching functions, because the value they fetch is always relative to the current row. The other two fetching functions are FIRST_VALUE and LAST_VALUE. FIRST_VALUE returns the first value in the table or partition, while LAST_VALUE returns the last value in the table or partition. These two functions are absolute, because what they return isn't dependent on the current row, and is absolute with respect to the table or partition.

3. LEAD
01:00 - 01:43
Let's start with the relative functions. This query returns the cities in which each set of Olympic Games was held, as well as the next two cities. Passing 1 as n to LEAD will get the next city, and passing 2 as n will get the city after that. In a way similar to LAG, LEAD will return null once it runs out of following rows. In this query, the last row will have a Next_City of null, since there's no row after it to fetch its value, and the next-to-last row will have an After_Next_City of null, since LEAD-City-2 fetches the value two rows after the current row, and that row for the next-to-last row doesn't exist.

4. FIRST_VALUE and LAST_VALUE
01:43 - 02:47
On to the absolute functions. This query is similar to the last, except it gets the first and last cities in which the Olympic Games were held in this table. The first Summer Olympic Games were held in Athens, and since 2012 is the last year that this dataset covers, London is the last city in which the games were held. FIRST_VALUE's syntax is pretty standard for window functions, but LAST_VALUE's syntax is new. Aside from the normal ORDER BY clause, there's a RANGE BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING. What does this mean? By default, a window starts at the beginning of the table or partition and ends at the current row. Without the RANGE BETWEEN clause, LAST_VALUE will get the value of the current row, so Last_City will be the same as City. The RANGE BETWEEN clause extends the window to the end of the table or partition so that the actual last value will be fetched. You'll learn more about this clause in the next chapter.

5. Partitioning with LEAD
02:47 - 03:22
So far, you've seen the functions used over the entire table, but what happens if you want to partition? These two tables fetch the current and next champions of the Discus Throw and Triple Jump events, but the left table doesn't partition by event, while the right table does. Since the left table isn't partitioned, Discus Throw's last row will fetch Triple Jump's first champion, which isn't right. Partitioning by event will correctly set Discus Throw's last row's next champion to be null, since Discus Throw's partition ends there.

6. Partitioning with FIRST_VALUE
03:22 - 03:43
Similarly, in the left table, the table isn't partitioned by event, so LTU will be Triple Jump's First_Champion even though it's in Discus Throw. The right table IS partitioned by event, so SWE will correctly be set as Triple Jump's First_Champion. Partitioning with LAST_VALUE works much the same way.

7. Let's practice!
03:43 - 03:50
Let's practice using the fetching functions to move values from one row to another.

**LINK** https://rpubs.com/cliex159/PostgreSQLSummaryStatsandWindowFunctions
