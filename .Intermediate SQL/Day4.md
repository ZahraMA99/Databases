## Filtering numbers :mushroom:
**Welcome back! Now that we've mastered selecting and counting data from a database, we'll add to our repertoire by learning about filtering.**

## WHERE :leaves:
- To filter, we need to use a new clause called WHERE, which allows us to focus on only the data relevant to our business questions.
- Going back to our coat analogy, we may want to select a coat from the closet

## WHERE :chestnut:
- where the color is green. The WHERE clause can help us with that.

## WHERE with comparison operators :sun_with_face:
- We will focus on filtering numbers in this lesson.
- To do this, we will be using comparison operators such as greater than.
- Here is an example of a query where we filtered to see only films released after the year 1960 using the greater than operator.
```js
//Select the film_id and imdb_score from the reviews table and filter on scores higher than 7.0.
SELECT film_id, imdb_score
FROM reviews
WHERE imdb_score > 7.0;
```

## Comparison operators :new_moon:
- Let's explore some of the other operators. We would use the less-than operator to see films released before the year 1960.
```js
// Select film_ids and facebook_likes for ten records with less than 1000 likes 
SELECT film_id, facebook_likes
FROM reviews
WHERE facebook_likes < 1000
LIMIT 10;
```

## Comparison operators :earth_asia:
- We would use the less than or equal to operator to see films released during or before the year 1960.

## Comparison operators :seedling:
- If we want to see films released in a specific year, we can use equals.
```js
// Count how many records have a num_votes of at least 100,000; use the alias films_over_100K_votes.
SELECT Count(num_votes) AS films_over_100K_votes
FROM reviews
WHERE num_votes >= 100000;
```

## Comparison operators :palm_tree:
- Here is a final example that isn't as intuitive as the others.
- If we wanted to filter films to see all releases EXCEPT those from the year 1960, we would combine the less than and greater than symbols as shown here.
- This is the SQL standard symbol that means "not equal to".

## Comparison operators :tulip:
- Let's recap all the comparison operators we can use with WHERE to filter numbers.
- We have:
1. greater than (that also means after)
2. less than (that also means before),
3. equal to,
4. greater than or equal to,
5. less than or equal to,
6. not equal to.

## WHERE with strings :paw_prints:
- WHERE and the comparison operator, equals, can also be used with strings.
- In these cases, we will have to use single quotation marks around the strings we want to filter.
- For example, here, we want to filter titles where the country is Japan.
```js
// Select and count the language field using the alias count_spanish and Apply a filter to select only Spanish from the language field.
SELECT Count(language) AS count_spanish
FROM films
WHERE language = 'Spanish';
```

## Order of execution :hibiscus:
- A final note on using WHERE. Similar to LIMIT, this clause comes after the FROM statement when writing a query.
- If we use both WHERE and LIMIT, the written order will be SELECT, FROM, WHERE, LIMIT; however, the order of execution will now be FROM, WHERE, SELECT, LIMIT.
- Thinking about the coats in our closet, we go to the closet we want to get the coat from, find where the green coats are, and select five of them.
