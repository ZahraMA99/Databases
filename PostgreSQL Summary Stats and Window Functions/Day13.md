1. A survey of useful functions
00:00 - 00:09
There are a couple of functions that'll make your life easier when dealing with window functions and pivoting. Let's explore two of them in this video.

2. Nulls ahoy
00:09 - 00:25
Recall this query from the ROLLUP and CUBE video. Also recall that the nulls in the output signify group totals. What if you want to replace the nulls with something that actually indicates that these rows are group totals?

3. Enter COALESCE
00:25 - 00:56
Enter COALESCE. COALESCE takes a list of values and returns the first non-null value, going from left to right. COALESCE is useful when using SQL operations that return nulls, such as ROLLUP and CUBE. Other operations that return nulls are pivoting (when some of your rows don't have any corresponding values for the new columns) and positional operations like LAG, which always returns a null for the first row, because it has no previous row.

4. Annihilating nulls
00:56 - 01:33
The only change to the previous query you need to make is to wrap the two columns with the COALESCE function, and pass it the string you want the column to contain if its value is null. The Country column is null when it's the grand total, so the string should be Both countries, whereas the Medal column is null when it's the count of all medals, so it should be All medals. Make sure to name the output columns as the columns you passed as their first argument for consistent results. As you can see in the output, the nulls have been replaced by what was passed in each COALESCE.

5. Compressing data
01:33 - 02:11
Let's move on to another common issue. In the before table, you have the rankings of these three countries in the 2012 Olympics by their count of gold medals in Gymnastics events. Notice that when you sort by Rank, Rank becomes redundant, since the sort order implies Rank -- the first rank is the first row; the second rank is the second row, and so on. Instead of returning three rows and two columns, you could return one row with a list of each country; the first country is the leftmost one, and so on. How can you compress data like that in SQL?

6. Enter STRING_AGG
02:11 - 02:29
Enter STRING_AGG. STRING_AGG takes all the values of a column and concatenates them, with a separator in between each value. It transforms this... into this. STRING_AGG is useful when you need to reduce the number of rows returned.

7. Query and result
02:29 - 02:55
The before query returns the before table from two slides ago. It should be pretty familiar by now. To use STRING_AGG, simply wrap the final query of the before query in a CTE called Country_Ranks. Then, use STRING_AGG on the Country column, and pass it a separator of a comma with a space after it. You'll get the clean result that you see below.

8. Let's practice!
02:55 - 03:06
Using COALESCE and STRING_AGG, you can clean and compress your queries' results. Let's practice using these two functions in the following exercises.
