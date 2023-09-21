1. Frames
00:00 - 00:11
With the PARTITION and ORDER subclauses, you can change the basis on which window functions operate. Another way to change a window function's behavior is to define a frame.

2. Motivation
00:11 - 00:50
Why would you need a frame? Recall the fetching function LAST_VALUE from the previous chapter. The frame here is RANGE BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING. Without the frame, LAST_VALUE would just return the row's value in the City column, so the City and Last_City columns would have the same value. That's because, by default, a frame starts at the beginning of a table or partition and ends at the current row, so the last row LAST_VALUE sees is the current row. The frame clause above extends the frame to the end of the table.

3. ROWS BETWEEN
00:50 - 01:57
How do you define a frame? A frame always starts with RANGE BETWEEN or ROWS BETWEEN. You'll learn the difference between RANGE and ROWS in the next video, but for now, let's focus on ROWS. A frame always has a start and a finish. Start and finish can be one of 3 clauses: PRECEDING, CURRENT ROW, and FOLLOWING. n PRECEDING defines the frame as either starting or finishing n rows before the current row. CURRENT ROW is to set the start or finish at the current row, and n following is to set it at n rows after the current row. Let's see some examples. This frame starts 3 rows before the current row and ends at the current row, so the frame is 4 rows. This frame starts one row before the current row and ends one row after the current row, so the frame is 3 rows. This frame starts five rows before the current row and ends one row before the current row, so the frame is 5 rows.

4. Source table
01:57 - 02:07
Let's see how a frame affects the output of a window function. The source table is the count of gold medals earned by Russia in these sets of Olympic games.

5. MAX without a frame
02:07 - 02:28
The MAX window function is used on the Medals column. Without the ROWS BETWEEN clause, MAX would get the maximum medals earned so far for any given year. For the first year, since there's no other value, the max is the first row's value, but for the second row onwards, the max is 66, since no other value is higher.

6. MAX with a frame
02:28 - 02:54
With the ROWS BETWEEN clause, since the frame is defined as starting one row before the current row and ending at the current row, MAX only gets the maximum of the values in the previous and and current rows. That's why in 2008 the max is 47 and not 66, since the 2000 Olympics are now out of scope, and MAX is only looking at the previous and current rows to get the maximum value.

7. Current and following rows
02:54 - 03:17
You can also "look forward" in frames. Here, the frame starts at the current row and ends at the following row, so in the first row, the maximum is 66, since MAX is comparing the 1996 and 2000 Olympics. The last row's max is the last row's value because there's no following row, so there's no value to compare it to.

8. Let's practice!
03:17 - 03:31
Frames enable you to change the behavior of a window function by defining what rows the window function takes as input. Practice defining frames in the following exercises.

**LINK** https://rpubs.com/cliex159/PostgreSQLSummaryStatsandWindowFunctions
