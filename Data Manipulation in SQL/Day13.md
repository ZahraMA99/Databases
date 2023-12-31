1. Window Partitions
00:00 - 00:14
You've done a great job working with the OVER clause so far! The real bread and butter of window functions that differentiates them from subqueries in select, are in the functions you can add within the OVER clause.

2. OVER and PARTITION BY
00:14 - 01:08
One important statement you can add to your OVER clause is PARTITION BY. A partition allows you to calculate separate values for different categories established in a partition. This is one way to calculate different aggregate values within one column of data, and pass them down a data set, instead of having to calculate them in different columns. The syntax for a partition is fairly simple. Just like before, use an aggregate function to compute a calculation, such as the AVG of the home_goal column. You then add the OVER clause afterward, and inside the parentheses, state PARTITION BY, followed by the column you want to partition the average by. This will then return the overall average for, or PARTITIONed BY each season.

3. Partition your data
01:08 - 01:33
Let's take a look at how this works in a query. This is the example query from the previous lesson, answering the question, "How many goals were scored in each match, and how did that compare to the overall average?" This is accomplished using the OVER clause, and the query returns the date, goals scored, and overall average.

4. Partition your data
01:33 - 02:24
Let's expand on the previous question, and instead ask, "How many goals were scored in each match, and how did that compare to the season's average?" We can do this by adding a PARTITION BY clause to the OVER clause from the previous slide. Specifying, "PARTITION BY season" returns each season's average on each row, in accordance to the season that each record belongs to. As you can see, rows 1 and 2 are matches played in the 2011/2012 season, and the season_avg column contains the 2011/2012 season average. Rows 3 and 4 are part of the 2012/2013 season, and return the 2012/2013 season average.

5. PARTITION by Multiple Columns
02:24 - 03:05
You can also use PARTITION to calculate values broken out by multiple columns. In the query you see here, the OVER clause contains two columns to partition the AVG goals scored--season, and country. The result set returns the average goals scored broken out by season and country. In row 1, a match was played in Belgium in the 2011/2012 season, and had 1 goal scored throughout the match. This is compared to the 2.88, which is the average goals scored in Belgium in the 2011/2012 season.

6. PARTITION BY considerations
03:05 - 03:29
PARTITION BY is a pretty straight forward addition to the OVER clause. You can partition calculations by 1 or more columns as necessary to answer a question you may have. Additionally, you can use a PARTITION with any kind of window function -- calculation, rank, or others that we will discuss further in the following lesson.

7. Let's practice!
03:29 - 03:38
For now, let's practice calculating window partitions on our match data.

**LINK:** 
