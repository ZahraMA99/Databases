1. Moving averages and totals
00:00 - 00:10
One of the most common uses for aggregate window functions with frames is the calculation of moving averages and totals. Let's see how that's done.

2. Overview
00:10 - 01:10
A moving average is the average of the last n periods of a column's values. Moving averages are used in a variety of industries. For example, in sales, the 10-day moving average is the average of the last ten days' units sold per day. It's used to indicate momentum and trends; if a day's units sold is higher than its moving average, then the next day, more units are likely to be sold. Moving averages are also useful in eliminating seasonality, the normal fluctuation of units sold per day. A moving total, on the other hand, is the sum of the last n periods of a column's values. For example, the sum of the last 3 Olympic games' medals for any given set of Olympic games. It's used to indicate performance in the recent periods; if the sum is going down, overall performance is going down, and vice-versa.

3. Source table
01:10 - 01:19
Let's see moving averages and totals in action. The source table is the count of gold medals awarded to the US after 1980.

4. Moving average
01:19 - 01:57
Let's get the 3-year moving average, which is the average of medals earned in the last two and the current sets of Olympic games for each year. Defining the window as starting two rows before the current row and ending at the current row will pass as input these three rows to the AVG function. The first moving average is equivalent to the first year's awarded medals, since there's no other value to average. The second row's moving average is the average of its value and the first row's value; the third row's moving average is the average of its value and the previous two rows, and so on.

5. Moving total
01:57 - 02:24
A moving total works in much the same way that the moving average does, but instead of the AVG function, you use the SUM function with the same frame. Thus, the first row's moving total is the first row's value, the second row's moving total is the sum of the first and second rows, and then each subsequent rows' moving total is the sum of its value and the values of the previous two rows.

6. ROWS vs RANGE
02:24 - 03:29
Recall from the previous video that LAST_VALUE's frame subclause starts with RANGE BETWEEN, whereas the frames you've seen so far start with ROWS BETWEEN. What's the difference? RANGE BETWEEN functions much the same as ROWS BETWEEN, with one major difference. RANGE treats duplicates in the columns in the ORDER BY subclause as single entities, whereas ROWS does not. Assume that you have this table of medals earned per year. Both Rows_RT and Range_RT columns are running totals, but the former uses ROWS to define its frame and the other uses Range. The Rows_RT column has the values you'd expect, but the Range_RT column treats the rows with duplicate values as single rows, summing them up first then displaying that sum for each duplicate row. They both arrive at the same cumulative sum, but how they get there is different. In practice, ROWS BETWEEN is almost always used over RANGE BETWEEN.

7. Let's practice!
03:29 - 03:35
Let's practice writing queries to calculate moving averages and totals in the following exercises.

**LINK** 
