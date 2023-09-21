1. Pivoting
00:00 - 00:17
Window functions give you information that you can't get with a GROUP BY, but they don't fundamentally change the structure of your result. What if you want to transform ranking data from a vertical to a horizontal structure, making it easier to scan?

2. Transforming tables
00:17 - 00:51
Pivoting transforms a table by making columns out of the unique values of one of its columns. The before table here represents the gold medals awarded to these three countries in the 2008 and 2012 Olympics. Once this table is pivoted by year, that column's unique values, 2008 and 2012, become columns in the after table. The values are automatically placed in the reshaped table. In general, pivoted tables are easier to scan, especially if pivoted by a chronologically ordered column.

3. Enter CROSSTAB
00:51 - 01:34
How do you do this in SQL, though? Enter CROSSTAB. CROSSTAB allows you to pivot a table by a certain column. You'll need to use the CREATE EXTENSION statement before using CROSSTAB. CREATE EXTENSION makes extra functions in an extension available for use. The tablefunc extension contains the CROSSTAB function. After that, place your source query in between the two dollar sign pairs. Finally, in the parentheses after ct, write the column names and types of your new pivoted table. The column names are the unpivoted column and the unique values of the pivoted column. Let's see this in action.

4. Queries
01:34 - 02:01
The before query generates the before table from two slides ago. After the CREATE EXTENSION statement, the before query is placed entirely between the two dollar sign pairs. The table is pivoted by Year, and the table's values are in the Awards column, so the columns are the unpivoted column (Country) and the unique values in the Year column (2008 and 2012). This query generates the after table from two slides ago.

5. Source query
02:01 - 02:31
How would you use pivoting with window functions? Let's take an example. This query should be pretty familiar. The CTE counts the gold medals awarded to three countries in the 2004, 2008, and 2012 Olympics. Then, each country's rank is calculated according to who won the the most gold medals in each Olympic games. Cast RANK to integer to determine the column type of the pivoted columns.

6. Source result
02:31 - 02:41
This is the result. Notice that the rankings reset after each Olympic games. Wouldn't this be easier to read if it were pivoted by year?

7. Pivot query
02:41 - 03:09
Replace the ellipsis with the source query from two slides back. Then, in the parentheses after ct, list the pivoted table's column names and types. Since you're pivoting by year, and the values are in Awards, the columns are Country (the unpivoted column) and the unique values in Year (2004, 2008, and 2012). Make sure to list the unique values in correct order.

8. Pivot result
03:09 - 03:15
This is the result. The rankings are easily scannable by country and year now.

9. Let's practice!
03:15 - 03:26
Pivoting is useful when preparing data for visualization and reporting. Let's practice reshaping tables in the following exercises.

**LINK** 
