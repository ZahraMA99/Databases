1. Introduction
00:00 - 00:14
Welcome to the course! My name is Michel Semaan. I created this course together with Fernando Gonzalez Prada, owner of FGP Database and Analytics. I'll be your instructor for this course.

2. Motivation
00:14 - 00:49
Before diving into the course, let's explore why you'd want to learn window functions. The left table contains a running total of US gold medals since 2004, and the right contains the previous and current Discus Throw champions. To calculate running totals and fetch previous rows' values without window functions, you'd have to write long, slow, and complex queries with multiple self-joins and subqueries. With window functions, you simply use one extra function, and you can calculate running totals or fetch previous rows' values.

3. Course outline
00:49 - 01:24
Let's go over the course's outline. In chapter 1, you'll learn what window functions are, the most common clauses that go with these functions, and two basic window functions. In chapter 2, you'll learn how to fetch, rank, and bin values in rows. In chapter 3, you'll learn to use familiar aggregate functions, such as SUM, as window functions, as well as how to define frames. Finally, in chapter 4, you'll learn techniques and functions that are useful when used with window functions.

4. Summer olympics dataset
01:24 - 01:41
Throughout this course, you'll query the Summer Olympics dataset, with each row representing an awarded medal. The columns contain the year, city, sport, discipline, event, athlete name, country, gender, and type of medal awarded.

5. Window functions
01:41 - 02:31
Let's dig in. Window functions perform an operation across a set of rows that are somehow related to the current row, which is the row the window function's currently operating on. They're similar to GROUP BY aggregate functions in that they span multiple rows, but instead of rows being grouped into a single row, all rows remain in the output. What are window functions used for? With window functions, you can easily do multiple things that are either quite complex or borderline impossible in SQL otherwise. For example, you can fetch values from rows before or after the current row. This could be used to determine if a competition's champion is reigning and to calculate growth over time. You can also assign ranks to rows, and calculate running totals and moving averages.

6. Row numbers
02:31 - 02:53
The most basic thing you can do with a window function is assign row numbers. Row numbers allow you to reference a row by its position or index as opposed to its values. You can fetch the 5th row no matter what its values are, for example. Assigning row numbers to this query's result would add an additional column with each row's number. How do you add this extra column?

7. Enter ROW_NUMBER
02:53 - 03:08
Enter ROW_NUMBER. ROW_NUMBER assigns a number to each row. The OVER clause indicates that it's a window function. In this query, ROW_NUMBER simply adds a column with each row's number or index.

8. Anatomy of a window function
03:08 - 03:37
Let's go over the anatomy of a window function like ROW_NUMBER. The OVER clause indicates that a function is a window function. The parentheses after OVER can be empty, just like the previous example, but they can also contain subclauses, such as ORDER BY, PARTITION BY, and ROWS or RANGE PRECEDING, FOLLOWING, or UNBOUNDED. These subclauses radically change the window function's output, and you'll learn about them in following videos.

9. Let's practice!
03:37 - 03:44
Now that you've been introduced to window functions, practice using them in the following exercises.

