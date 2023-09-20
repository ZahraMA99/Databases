1. EXCEPT
00:00 - 00:07
Way to go! We are now at the last of our set operations in this course.

2. EXCEPT Venn diagram
00:07 - 00:21
EXCEPT allows us to identify the records that are present in one table, but not the other. More specifically, it retains only records from the left table that are not present in the right table.

3. EXCEPT diagram
00:21 - 00:49
The diagram shown illustrates the workings of the EXCEPT operation. All records that are not of interest to the EXCEPT operation are faded out. Only the last two records of the left_table are returned. Note that while the id 4 does exist in the right_table, the whole record does not match, which is why the last record of left_table is not faded out.

4. EXCEPT syntax
00:49 - 01:28
We saw earlier that there are some monarchs that also act as the prime minister for their country. Let's say we were interested in monarchs that do NOT also hold the title of prime minister. The EXCEPT clause is really handy for this! The SQL code shown selects the monarch and country field from monarchs and then looks for common entries in the prime_minister and country fields in the prime_ministers table, looking to exclude those entries. In the result, we see only the three monarchs from our leaders database who do not also serve the role of prime minister.

5. Let's practice!
01:28 - 01:38
Well done getting through all the lessons on set operations.

**LINK:** https://iqraanwar.medium.com/09-set-theory-for-sql-joins-ac199f4aa335
