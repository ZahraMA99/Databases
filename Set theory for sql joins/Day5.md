1. Subqueries inside WHERE and SELECT
00:00 - 00:12
In this lesson, we'll dive deeper into embedding queries within queries. We'll revisit subqueries within a WHERE clause, and then go on to subqueries within a SELECT statement.

2. Syntax for subqueries inside WHERE
00:12 - 00:42
The semi joins and anti joins we have seen so far involve subqueries inside WHERE. The WHERE clause is the most common place for subqueries, because filtering data is one of the most common data manipulation tasks. Let's revisit this with some generic syntax and understand the nuances of this type of subquery. Have a look at the query shown. Recall that the WHERE IN clause enables us to provide a list of values to filter on.

3. Syntax for subqueries inside WHERE
00:42 - 01:02
As we have seen in the lesson on semi joins, arguments to the IN operator are not limited to lists typed out by us. We can include a SQL subquery as an argument for the IN operator, provided the result of the subquery is of the same data type as the field we are filtering on.

4. Syntax for subqueries inside WHERE
01:02 - 01:24
The query shown will only work if some_field is of the same data type as some_numeric_field, because the result of the subquery will be a numeric field. Subqueries inside WHERE can be from the same table or from a different table, and here, the subquery is from a different table.

5. Subqueries inside SELECT
01:24 - 01:46
The second most common type of subquery is inside a SELECT clause. Say we want to count the number of monarchs listed in the monarchs table for each continent in the states table. Again, let's build up our solution, step by step. The query shown selects each of the five continents in the states table, and the result is displayed.

6. Subqueries inside SELECT
01:46 - 02:35
In earlier courses we have seen the use of GROUP BY to COUNT data by a group. However, since our monarchs data lives in a different table than the states table, this would involve a careful join before the GROUP BY. Let's look at how to do this with a subquery instead. Our subquery requires two things. First, it needs to COUNT all monarchs. Second, it needs a WHERE statement matching the continent fields in the two tables. This subquery follows the selection of DISTINCT continents, and will therefore count all monarchs within them in the SELECT statement. A subquery inside a SELECT statement like this requires an alias, like monarch_count here. Magic!

7. Let's practice!
02:35 - 02:46
Test your subquery expertise with a few exercises! See you in the next video on subqueries inside the FROM clause.

**LINK:** https://iqraanwar.medium.com/10-subqueries-aa0f8310ce38
