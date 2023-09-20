1. Subquerying with semi joins and anti joins
00:00 - 00:14
We've made it to the final chapter of this course! Keep up the excellent work. In this lesson, we'll return to joins one last time, with an introduction to nested SQL queries.

2. Calling all joins
00:14 - 00:30
The six joins we've worked with so far are all "additive" in that they add columns to the original "left" table. The diagram shows an INNER JOIN on the id field, showing an additional column being added to the original left table.

3. Additive joins
00:30 - 00:41
Here is some familiar INNER JOIN syntax for this join on the id field. Lets dive deeper into what it means for this join to be "additive".

4. Additive joins
00:41 - 01:01
Fields with different names are added to the result set with their original names. Fields with the same name, such as date, are added to the result set too, but notice how we now have duplicate date columns with the same name. This can be changed, however, with aliasing.

5. Semi join
01:01 - 01:31
In this lesson, we'll see ways of joining data that do not expressly use JOIN keywords and are not additive in the same way. Instead of using JOIN or set operators, we can leverage the WHERE clause to specify the records to include. We'll use the two tables, left_table and right_table, in the diagram shown. A semi join chooses records in the first table where a condition is met in the second table.

6. Semi join
01:31 - 01:47
More specifically, the semi join will return all values of left_table where values of col1 are in a column we specify, namely col2 in the right_table. Records not of interest to the semi join have been faded out.

7. Semi join
01:47 - 01:54
The final result of our semi join is records corresponding to ids 2 and 3.

8. Kicking off our semi join
01:54 - 02:17
Let's make this concrete with an example. Suppose we are interested in determining the presidents of countries that gained independence before 1800. We select the fields country, continent, and president. How do we filter this data for independence year, which is a field in the states table? We'll use a semi join!

9. Building on our semi join
02:17 - 02:36
Before we knew anything about joins, we knew we could leverage the WHERE clause to filter data. The query that returns countries with indep_year before 1800 is shown. The query returns only Spain and Portugal from our database.

10. Finish the semi join (an intro to subqueries)
02:36 - 02:57
We can use this list of countries as a filter by embedding it in a further WHERE clause. This is called a subquery! It chooses records in the first table where the country matches the list returned by our subquery. Since Spain does not have a president, only the Portuguese president is listed.

11. Anti join
02:57 - 03:06
Moving on to anti joins! The anti join chooses records in the first table where col1 does NOT find a match in col2.

12. Anti join
03:06 - 03:17
The final result of our anti join is records corresponding to ids 1 and 4. Again, no new columns are added.

13. An anti join with the presidents
03:17 - 04:05
How might we adapt our semi join to determine countries in the Americas founded after 1800? To change our semi join from before to after 1800, we add NOT before the IN statement. We call this an anti join! In addition, we add to our first WHERE clause to filter for continents in the Americas. The result shows presidents of countries in the Americas that gained independence after 1800. Only Chile and Uruguay are returned, not the USA, which gained independence before 1800. Note again that we are only using the few countries in our database for illustration; this is not a comprehensive list of countries in the world!

14. Let's practice!
04:05 - 04:09
Let's practice!

**LINK**: https://iqraanwar.medium.com/10-subqueries-aa0f8310ce38
