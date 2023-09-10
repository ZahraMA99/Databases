## Data :ocean:
**Welcome to the final part of the databases chapter! This lesson will focus on the data inside a database as well as its storage.**

## SQL data types :mushroom:
When a table is created, a data type must be indicated for each field.<br/>
The data type is chosen based on the type of data that the field will hold - a number, text, or a date for example.<br/>
We use data types for several reasons.<br/>
1. Different types of data are stored differently and take up different amounts of storage space.
2. Some operations only apply to certain data types.
> It makes sense to multiply a number by another number, but it does not make sense to multiply text by other text for example.

## Strings :seedling:
**In programming, a "string" refers to a sequence of characters such as letters or punctuation.** 
- On the patrons table, the data in the names field is made up of strings, such as "Maham" and "James".<br/>
- SQL has several different data types that can hold strings.<br/>
- Some string data types can only hold short strings, such as a string up to 250 characters.<br/>
- Storing short strings in a small data type like this saves storage space.<br/>
- SQL's VARCHAR data type is more flexible and can store small or large strings - up to tens of thousands of characters! Because of its flexibility, VARCHAR is very commonly used for storing strings.
