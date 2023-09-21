1. Common Table Expressions
00:00 - 00:06
Great job getting the hang of nested and correlated subqueries.

2. When adding subqueries...
00:06 - 00:30
As you probably noticed, the queries we have been setting up are quickly becoming long and complex. It can become difficult to clearly keep track of each piece of your query, why you need it, and whether or not it's necessary. In this lesson, we'll cover a common method for improving readability and accessibility of information in subqueries -- the common table expression.

3. Common Table Expressions
00:30 - 00:55
Common table expressions, or CTEs are a special type of subquery that is declared ahead of your main query, just like you see here. Instead of wrapping subqueries inside, say the FROM statement, you name it using the WITH statement, and then reference it by name later in the FROM statement as if it were any other table in your database.

4. Take a subquery in FROM
00:55 - 01:35
Let's rewrite a query from an exercise that you completed in chapter 2, by using a CTE. The query you see here uses a subquery, s, in the FROM statement to generate a list of country id's and match IDs that meet a certain criteria -- specifically, we only wanted matches with 10 or more goals scored in total. This subquery is then joined to the country table, and the number of matches in the subquery is counted in the main query. Here are the results of that query -- a short list of countries with very few high-scoring matches.

5. Place it at the beginning
01:35 - 01:48
In order to rewrite this query using a common table expression to represent the subquery, simply take the subquery out of the FROM clause, place it at the beginning of your query,

6. Place it at the beginning
01:48 - 02:09
declare it using the syntax WITH, followed by a CTE name, and AS. So, here we're starting our CTE, s, by stating WITH s AS, and then placing the subquery inside parentheses. It's now a common table expression!

7. Show me the CTE
02:09 - 02:39
Finally, complete the rest of the query the same way you would if the CTE were an existing table in the database. You select the country name from the country table, count the number of matches in the CTE "s", JOIN "s" to the country table, and then group the results by the country name's alias. The results -- you guessed it -- are identical to the previous query setup!

8. Show me all the CTEs
02:39 - 03:04
If you have multiple subqueries that you want to turn into a common table expression, you can simply list them one after another, with a comma in between each CTE, and NO comma after the last one. You can then retrieve the information you need into the main query -- just make sure you properly join this second CTE as well!

9. Why use CTEs?
03:04 - 04:08
So why are we learning yet another method of producing the same result in a SQL query? Common table expressions have numerous benefits over a subquery written inside your main query. First, the CTE is run only once, and then stored in memory, so it often leads to an improvement in the amount of time it takes to run your query. Second, CTEs are an excellent tool for organizing long and complex CTEs. You can declare as many CTEs as you need, one after another. You can also reference information in CTEs declared earlier. For example, if you have 3 CTEs in a query, your third CTE can retrieve information from the first and second CTE. Finally, a CTE can reference itself in a special kind of table called a recursive CTE. We'll briefly discuss some more advanced applications of CTEs in the next lesson.

10. Let's practice!
04:08 - 04:20
For now, let's practice writing CTEs by modifying queries in exercises you completed in chapter 2.

**LINK:** https://rpubs.com/cliex159/IntermediateSQL
