1. Subqueries everywhere! And best practices!
00:00 - 00:20
Now that you've covered the ways in which you can use subqueries in the SELECT, FROM, and WHERE clauses, let's look at the use of multiple subqueries in one query, and some best practices for making sure your queries are as readable as possible.

2. As many subqueries as you want...
00:20 - 00:57
In SQL, you can include as many simple subqueries as you need within multiple clauses within your query. However, your queries can quickly become long, and difficult to read. For example, the query you see here includes a subquery in the SELECT, FROM, and WHERE statements. You don't have to read through this now, but it's worth getting a sense of how extensive SQL queries can get, and discuss some best practices for reading, and writing large queries.

3. Format your queries
00:57 - 01:28
The best practice you can start early on in your SQL journey is properly formatting your queries. It's important to properly line up your SELECT, FROM, GROUP BY, and WHERE statements, and all of the information contained in them. This way, you and others you work with can return to a saved query and easily tell if these statements are part of a main query, or a subquery.

4. Annotate your queries
01:28 - 01:48
It's also considered best practice to annotate your queries with comments in order to tell the user what it does -- using either a multiple line comment, inside a forward slash, star, and ending with a star, and a forward slash.

5. Annotate your queries
01:48 - 02:03
You can also use in-line comments using two dashes. Every piece of information after an in-line comment is treated as text, even if it's a recognized SQL command.

6. Indent your queries
02:03 - 02:29
Additionally, make sure that you properly indent all information contained within a subquery. That way, you can easily return to the query and understand what information is being processed first, where you need to apply changes, such as to a range of dates, and what you can expect from your results if you make those changes.

7. Indent your queries
02:29 - 03:08
Make sure that you clearly indent all information that's part of a single column, such as a long CASE statement, or a complicated subquery in SELECT. In order to best keep track of all the conditions necessary to set up each WHEN clause, each THEN clause, and how they create the column outcome, it's important to clearly indent each piece of information in the statement. Overall, I highly recommend you read Holywell's SQL Style Guide to get a sense of all the formatting conventions when working with SQL queries.

8. Is that subquery necessary?
03:08 - 03:41
When deciding whether or not you need a subquery, it's important to know that each subquery you add requires additional computing power to generate your results. Depending on the size of your database and the number of records you extract in your query, you may significantly increase the amount of time it takes to run your query. So it's always worth asking whether or not a specific subquery is necessary to get the results you need.

9. Properly filter each subquery!
03:41 - 04:21
Finally, when constructing a main query with multiple subquery, make sure that your filters are properly placed in every subquery, and the main query, in order to generate accurate results. The query here, for example, filters for the 2013/2014 season in 3 places -- once in the SELECT subquery, once in the WHERE subquery, and once in the main query. This ensures that all data returned is only about matches from the 2013/2014 season.

10. Let's practice!
04:21 - 04:31
Okay! Time to practice creating complex queries with multiple subqueries.

**LINK:** https://rpubs.com/cliex159/IntermediateSQL
