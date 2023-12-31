1. Set theory for SQL Joins
00:00 - 00:17
Welcome back for Chapter 3! In this chapter, we explore a new way of joining data: set operations. Along the way, we'll highlight key differences between set operations and the joins we have seen so far.

2. Venn diagrams and set theory
00:17 - 00:41
SQL has three main set operations, UNION, INTERSECT and EXCEPT. The Venn diagrams shown visualize the differences between them. We can think of each circle as representing a table. The green parts represent what is included after the set operation is performed on each pair of tables.

3. Venn diagrams and set theory
00:41 - 00:50
In this lesson, we will cover UNION and UNION ALL. Let's take a closer look at how they work.

4. UNION diagram
00:50 - 01:22
In SQL, the UNION operator takes two tables as input, and returns all records from both tables. The diagram shows two tables: left and right, and performing a UNION returns all records in each table. If two records are identical, UNION only returns them once. To illustrate this, the first two records of the right table have been faded out. Our result has seven records.

5. UNION ALL diagram
01:22 - 01:47
In SQL, there is a further operator for unions called UNION ALL. In contrast to UNION, given the same two tables, UNION ALL will include duplicate records. Therefore, performing UNION ALL on this data will return nine records, whereas UNION only returned seven. No records have been faded out.

6. UNION and UNION ALL syntax
01:47 - 02:27
The syntax for performing all the set operations in this chapter is highly similar. We perform a SELECT statement on our first table, a SELECT statement on our second table, and specify a set operation (in this example, either UNION or UNION ALL) between them. Note that set operations do not require a field to join ON. This is because they do not do quite the same thing as join operations we covered in earlier chapters. Rather than comparing and merging tables on the left and right, they stack fields on top of one another.

7. UNION and UNION ALL syntax
02:27 - 02:40
For all set operations, the number of selected columns and their respective data types must be identical. For instance, we can't stack a number field on top of a character field.

8. UNION and UNION ALL syntax
02:40 - 02:49
The result will only use field names (or aliases, if used) of the first SELECT statement in the query.

9. To the monarchs table
02:49 - 03:08
We now return to our world leaders example. In this example, we use one more table from our leaders database: the monarchs table. Of course, this table is only a sample of monarchs, and not a comprehensive list of monarchs across the world.

10. Prime ministers, meet the monarchs
03:08 - 03:35
We can use UNION on the monarchs and prime_ministers tables to show all the different prime ministers and monarchs in these two tables. Note that the monarch field has been aliased as 'leader'. As we have learned, the monarch and prime_minister fields will be combined under the leader field, even though we only aliased the monarch field. We'll LIMIT to the first 10 results so that they fit on our screen.

11. After the UNION
03:35 - 04:03
Our UNION returns the top 10 monarchs, prime_ministers and their corresponding countries. Does something stand out here? Recall that the monarchs for Oman and Brunei are also prime ministers. UNION only lists them once each, because they are the same person. Norway is listed twice, however, because its monarch and prime minister are different people.

12. UNION ALL with the leaders
04:03 - 04:15
This is where a UNION ALL is helpful! A UNION ALL will tell us if there are any monarchs who also act as prime ministers. The syntax for this is shown.

13. UNION ALL result
04:15 - 04:20
After UNION ALL, Brunei and Oman are now listed twice.

14. Let's practice!
04:20 - 04:29
Ready for some exercises? Let's look at some more applications of UNION compared to UNION ALL.

**EX. LINK**: https://iqraanwar.medium.com/09-set-theory-for-sql-joins-ac199f4aa335
