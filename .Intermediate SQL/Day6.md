## Filtering text :roller_coaster:
- We're making excellent progress! We will now switch our focus away from filtering numbers to filtering textual data.
- As we've briefly seen, we can use the WHERE clause to filter text data. However, so far, we've only been able to filter by specifying the exact text we're interested in.
- We'll often want to search for a pattern rather than a specific text string in the real world.
- We'll be introducing three more SQL keywords into our vocabulary to help us achieve this: LIKE, NOT LIKE, and IN.

## LIKE :ferris_wheel:
- In SQL, we can use the LIKE operator with a WHERE clause to search for a pattern in a field.
- We use a wildcard as a placeholder for some other values to accomplish this.
- There are two wildcards with LIKE, the percent, and the underscore.
- The percent wildcard will match zero, one, or many characters in the text.
- For example, the query on the left matches people like Adel, Adelaide, and Aden.
- The underscore wildcard will match a single character.
- For example, the query on the right matches only three-letter names like Eve.
- We'd also see names like Eva if it were in our dataset.
- Eva Mendes, however, would not be visible unless the search criteria looked like this.
```js
// Select the names that start with B
SELECT name
FROM people
WHERE name LIKE 'B%';

// Select the names of people whose names have 'r' as the second letter.
SELECT name
FROM people
WHERE name LIKE '_r%';

// Select the names of people whose names don't start with 'A'.
SELECT name
FROM people
WHERE name NOT LIKE 'A%';
```

## NOT LIKE :rocket:
- We can also use the NOT LIKE operator to find records that don't match the specified pattern.
- In this query, we are finding records for people who do not have A-dot as part of their first name.
- It's important to note that this operation is case-sensitive, so we must be mindful of what we are querying.

## Wildcard position :airplane:
- We've reviewed one example of where to position each wildcard, but we can actually put them anywhere and combine them!
- We can find values that start, end, or contain characters in any position, as well as find records of a certain length.
- For example, this code on the left will find all people whose name ends in r.
- The code on the right will find records where the third character is t.

## WHERE, OR :helicopter:
- What if we want to filter based on many conditions or a range of numbers?
- We could chain several ORs to the WHERE clause based on what we know, but that can get messy.
- We can see an example here where we select the film titles released in 1920, 1930, or 1940.

## WHERE, IN :tram:
- A helpful operator here is IN.
- The IN operator allows us to specify multiple values in a WHERE clause, making it easier and quicker to set numerous OR conditions.
- Neat, right? So, the example shown on the previous slide would simply become WHERE release_year IN 1920, 1930, 1940, where the years are enclosed in parentheses.
```js
// Select the title and release_year of all films released in 1990 or 2000 that were longer than two hours.
SELECT title, release_year
FROM films 
WHERE release_year IN (1990, 2000)
    AND duration > 120 ;

// Select the title and language of all films in English, Spanish, or French using IN.
SELECT title, language
FROM films
WHERE language IN ('English', 'Spanish', 'French');

// Select the title, certification and language of all films certified NC-17 or R that are in English, Italian, or Greek.
SELECT title, certification, language
FROM films 
WHERE (certification ='NC-17' OR certification = 'R')
    AND language IN ('English', 'Italian', 'Greek');
```

## WHERE, IN :tram:
- Here is another example using a text field where we want to find the title WHERE the associated country is either Germany or France.
