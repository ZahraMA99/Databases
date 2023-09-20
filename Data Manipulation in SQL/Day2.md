1. In CASE things get more complex
00:00 - 00:09
Now that you understand the basics of CASE statements, let's set up some more complex logical tests.

2. Reviewing CASE WHEN
00:09 - 00:44
Previously, we covered CASE statements with one logical test in a WHEN statement, returning outcomes based on whether that test is TRUE or FALSE. This example tests whether home or away goals were higher, and identifies them as wins for the team that had a higher score. Everything ELSE is categorized as a tie. The resulting table has one column identifying matches as one of 3 possible outcomes.

3. CASE WHEN ... AND then some
00:44 - 01:53
If you want to test multiple logical conditions in a CASE statement, you can use AND inside your WHEN clause. For example, let's see if each match was played, and won, by the team Chelsea. Let's see the CASE statement in this query. Each WHEN clause contains two logical tests -- the first tests if a hometead_id identifies Chelsea, AND then it tests if the home team scored higher than the away team. If both conditions are TRUE, the new column output returns the phrase "Chelsea home win!". The opposite set of conditions are included in a second when statement -- if the awayteam_id belongs to Chelsea, AND scored higher, then the output returns "Chelsea away win!". All other matches are categorized as a loss or tie. Here's the resulting table.

4. What ELSE is being excluded?
01:53 - 02:40
When testing logical conditions, it's important to carefully consider which rows of your data are part of your ELSE clause, and if they're categorized correctly. Here's the same CASE statement from the previous slide, but the WHERE filter has been removed. Without this filter, your ELSE clause will categorize ALL matches played by anyone, who don't meet these first two conditions, as "Loss or tie :(". Here are the results of this query. A quick look at it shows that the first few matches are all categorized as "Loss or tie", but neither the hometeam_id or awayteam_id belong to Chelsea.

5. Correctly categorize your data with CASE
02:40 - 03:20
The easiest way to correct for this is to ensure you add specific filters in the WHERE clause that exclude all teams where Chelsea did not play. Here, we specify this by using an OR statement in WHERE, which retrieves only results where the id 8455 is present in the hometeam_id or awayteam_id columns. The resulting table from earlier, with the team IDs in bold here, clearly specifies whether Chelsea was home or away team.

6. What's NULL?
03:20 - 03:44
It's also important to consider what your ELSE clause is doing. These two queries here are identical, except for the ELSE NULL statement specified in the second. They both return identical results -- a table with quite a few null results. But what if you want to exclude them?

7. What are your NULL values doing?
03:44 - 04:04
Let's say we're only interested in viewing the results of games where Chelsea won, and we don't care if they lose or tie. Just like in the previous example, simply removing the ELSE clause will still retrieve those results -- and a lot of NULL values.

8. Where to place your CASE?
04:04 - 04:20
To correct for this, you can treat the entire CASE statement as a column to filter by in your WHERE clause, just like any other column. In order to filter a query by a CASE statement,

9. Where to place your CASE?
04:20 - 04:50
you include the entire CASE statement, except its alias, in WHERE. You then specify what you want to include, or exclude. For this query, I want to keep all rows where this CASE statement IS NOT NULL. My resulting table now only includes Chelsea's home and away wins -- and I don't need to filter by their team ID anymore!

10. Let's practice!
04:50 - 04:59
Okay! Let's practice some more complex CASE statements.

**EX_LINK**: https://rpubs.com/cliex159/IntermediateSQL
