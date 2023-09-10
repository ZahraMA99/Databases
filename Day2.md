##  Tables :rainbow:
Main building block of databases: tables!

## A seat at the table :boat:
We saw in the previous lesson that databases are organized into tables, which hold related data about a particular subject.<br/>
tables are organized into rows and columns<br/>
**rows are often referred to as records and columns as fields.**

> A table's fields are limited to those set when the database was created, but the number of rows is unlimited.

## Good table manners :carousel_horse:
*Let's talk a little bit about table naming.* <br/>
**Table names should be lowercase and should not include spaces**
> we use underscores in place of spaces. And ideally, a table name would refer to a collective group (like "inventory")<br/> but it's also okay for the table to have a plural name (such as "products").

## Laying the table: records :notes:
**A record is a row in a table.** <br/>
It holds data on an individual observation.<br/>Taking a look at the patrons table, we see that the table has four records: one for each of the patrons. The record for Jasmin indicates that she became a member in 2022 and owes two dollars and five cents in fines.

## Laying the table: fields :notes:
**A field is a column in a table.** <br/>
it holds one piece of information about all observations in the table. The "name" field in the patrons table lists all of the names of our library patrons.

## More table manners :carousel_horse:
*Because field names must be typed out when querying a database with SQL, field naming is important.* <br/> 
1. Generally, field names should be lowercase and should not involve spaces.<br/> 
2. A field name should be singular rather than plural because it refers to the information contained in that field for a single record. This is why our table has "card_num" and
3. "name" fields rather than "card_nums" and "names". Similarly, two fields in a table cannot have the same name. Finally, field names should never share a name with the table they are housed in so that it's clear in all cases whether a field or table is being referred to.
4. It holds one piece of information about all observations in the table. The "name" field in the patrons table lists all of the names of our library patrons.

## Assigned seats :boat:
**A unique identifier, sometimes called a "key"** <br/>
is just what it sounds like: a unique value which identifies a record so that it can be distinguished from other records in the same table.<br/>
**This value is very often a number.** <br/>
In the patrons table, it makes sense to use the card_num field as the unique identifier for each patron, not the name field, because it's possible that as our little library grows, two patrons might have the same name.

