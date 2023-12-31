1. At the INTERSECT
00:00 - 00:07
Welcome back. In this lesson we'll explore our next set operation: INTERSECT.

2. INTERSECT Venn diagram
00:07 - 00:14
INTERSECT takes two tables as input, and returns only the records that exist in both tables.

3. INTERSECT diagram
00:14 - 00:33
In the diagram shown, we have two tables, left_table and right_table. The result of performing INTERSECT on these tables is only the records common to both tables: the first record. All records that are not of interest to the INTERSECT operation are faded out.

4. INTERSECT syntax
00:33 - 00:48
The syntax for this set operation is very similar to that of UNION and UNION ALL. We perform a SELECT statement on our first table, a SELECT statement on our second table, and specify our set operator between them.

5. INTERSECT vs. INNER JOIN on two columns
00:48 - 01:37
Let's compare INTERSECT to performing an INNER JOIN on two fields with identical field names. Similar to UNION, for a record to be returned, INTERSECT requires all fields to match, since in set operations we do not specify any fields to match on. This is also why it requires the left and right table to have the same number of columns in order to compare records. In the figure shown, only records where both columns match are returned. In INNER JOIN, similar to INTERSECT, only results where both fields match are returned. INNER JOIN will return duplicate values, whereas INTERSECT will only return common records once. As we know from earlier lessons, INNER JOIN will add more columns to the result set.

6. Countries with prime ministers and presidents
01:37 - 02:06
Let's have a look at how we can use INTERSECT to determine all countries that have both a prime minister and a president. Each SELECT statement in our query has the same number of columns, of identical data types, in order for the set operation to be performed. The result of the query is the four countries with both a prime minister and a president in our leaders database. As with UNION, the result set uses the field names provided for the left table, whether aliased or not.

7. INTERSECT on two fields
02:06 - 02:43
Next, let's think about what would happen if we selected two columns, country and prime_minister, instead of just country, as in our previous example. The code shown does just that. What will the result of this query be? Will this also give us the names of countries that have both a prime minister and a president? The actual result is an empty table. Why is that? As we saw in our INTERSECT diagrams, INTERSECT requires data from both fields in the left table to match their corresponding fields in the right table. The search did not find any countries where the prime minister and president share the same name.

8. Countries with prime ministers and monarchs
02:43 - 03:00
However, recall that there are monarchs in our database who also act as prime_ministers. In the example shown, performing an INTERSECT on the prime_ministers and monarchs tables using both country and leader name does not return an empty result.

9. Let's practice!
03:00 - 03:04
Let's get some practice!

**LINK:** https://iqraanwar.medium.com/09-set-theory-for-sql-joins-ac199f4aa335
