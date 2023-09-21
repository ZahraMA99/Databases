1. Paging
00:00 - 00:04
The third common application of window functions is paging.

2. What is paging?
00:04 - 00:49
Paging is splitting data into (approximately) equal chunks. APIs are interfaces to exchange data between different web platforms, and many APIs return data in "pages" to reduce the size of the data being sent, and make it more on demand. Also, when data is sorted by a metric, separating data into quartiles or thirds can help judge performance, since one can see whether a data point is in the top, middle, or bottom third. How do you paginate data in SQL? Enter NTILE. NTILE is a window function that takes as input n, then splits the data into n approximately equal pages. Let's see NTILE in action.

3. Paging - Source table
00:49 - 01:12
This query returns all 67 unique disciplines. Splitting them into 15 approximately equal pages will net around 4 or 5 rows in each page. The reason why the number of rows per page isn't constant is because 67 is not evenly divided by 15, so there will be overflow in some pages.

4. Paging
01:12 - 01:36
Place the previous query in a CTE, and use NTILE, passing 15 as n. In the result, the query's rows are split into 15 pages, with around four or five rows per page. For example, Page 1 has 5 rows, but Page 2 has four, though the results are truncated here for space.

5. Top, middle, and bottom thirds
01:36 - 02:23
Another use for NTILE is to split the data into thirds or quartiles. Here, the Country_Medals CTE counts the number of medals each country has been awarded overall in each set of Olympic Games. Using NTILE and passing 3 as n, and ordering by the medals awarded in descending order, the query's results will be split into thirds, with the top 33% of countries by medals awarded in the top third (with the Third column's value being 1), the middle 33% in the middle third (with the Third column's value being 2), and the bottom 33% in the bottom third (with the Third column's value being 3). This way, you can easily label the top, middle, or bottom x% of your data.

6. Thirds averages
02:23 - 02:37
Grouping by the Third column, you can see that the top third has an average count of awarded medals of almost 600; the middle third has an average of about 23, and the bottom third has an average of 2 medals.

7. Let's practice!
02:37 - 02:49
Now that you've seen the uses of NTILE in paging and labeling the top, middle, and bottom x% of your data, practice using it in the following exercises.

**LINK** https://rpubs.com/cliex159/PostgreSQLSummaryStatsandWindowFunctions
