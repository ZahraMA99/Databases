1. Deciding on techniques to use
00:00 - 00:10
At this point in the course, you're probably wondering why we're covering so many different methods of performing similar tasks.

2. Different names for the same thing?
00:10 - 00:34
That's a great question. The simplest answer is that yes, there is a lot of overlap between use cases for joins, subqueries, and common table expressions. Many questions that you answer can use these techniques interchangeably without sacrificing query run time or the accuracy of your output. But these techniques are not identical.

3. Differentiating Techniques
00:34 - 02:26
Let's take a minute to compare the techniques we've been using in this and the previous chapter. Joins allow you to directly combine information from 2 or more tables, and on their own, are mostly limited to simple combinations and aggregations of tables already present in your database. A correlated subquery allows you to combine information between a subquery and a table, or another subquery. These help you simplify your syntax and circumvent the limits of a join -- namely, that you can't join two separate columns in one table, to a single column in another at a time. We saw this in the "match" table, where you can't retrieve the team name from the "team" table for both the home and away teams at the same time. A correlated query can solve that problem. However, it's important to remember that correlated subqueries take a long time to process, and will slow down your query performance. Multiple and nested subqueries are useful when your data requires multi-step transformations before it's in the form you need for your final query. Breaking down the steps of your query process allows for better accuracy and reproducibility in your work. Finally, common table expressions allow you to organize your subqueries sequentially by declaring them at the beginning of your query. Since CTEs are processed one at a time before your main query, you can reference information from a CTE created earlier, thus serving as an alternative to nested subqueries.

4. So which do I use?
02:26 - 02:51
So which one do you use? Often, it really depends on the database you're using, the field that you're working in, and the questions that you're asking. In general, I recommend that you practice each technique with your own databases to determine which allows you to best use and reuse your queries and generate clear and accurate results.

5. Different use cases
02:51 - 04:13
Before we move on, I'll share a few examples of questions that each of these approaches can be used for. As you've seen, joins are a universally important skill when working with a database that has more than 1 table. It's fair to say that joins are necessary to understand each of the following techniques. Correlated subqueries are great for matching data from different columns in one or more tables, such as determining who each employee's immediate supervisor is. Multiple and nested subqueries are great for answering questions such as, what is the average deal size closed by each sales representative in the last quarter, which would require multiple steps to transform and prepare before generating the final query. Finally, CTEs are excellent for comparing a large number of disparate pieces of information. For example, you may want to create a summary table examining the marketing, sales, growth, and engineering teams' performance on their key metrics last quarter. With CTEs, you can extract data about each team's performance one after another, and combine them into a single query.

6. Let's Practice!
04:13 - 04:23
Okay! Let's practice some variations on these techniques to see what your results look like.

**LINK:** https://rpubs.com/cliex159/IntermediateSQL
