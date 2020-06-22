# W5D1 - SQL Intro

### To Do
- [x] Introduction to RDBMS
- [x] The Relational Data Model (Tables, Columns, Rows)
- [x] `SELECT` Statements
- [x] Filtering and ordering
- [ ] Joining tables
- [ ] Grouping records
- [ ] Aggregation functions
- [ ] `LIMIT` and `OFFSET`

### Databases
* Save and retrieve data
* Data persists

### RDBMS
* Relational DataBase Management System
* AKA the database server
* `psql` <--- REPL

Client <-----HTTP/TCP----> Server <----POSTGRES/TCP--> RDBMS

### Relational Database Model
* Table structure - rows and columns
* Rows === records, columns === fields (adjectives/properties)

Name    Price     Calories
Big Mac $3.99     680

```js
{
  name: 'Big Mac',
  price: 3.99,
  calories: 680
}
```






### SELECT Challenges

For the first 5 queries, we'll be using the `users` table.

![users table](https://andydlindsay-portfolio.s3.amazonaws.com/lighthouse/w5d1-users.io.png)

1. List total number of users

```sql
SELECT COUNT(*) 
FROM users;
```

2. List users over the age of 18

```sql
SELECT * 
FROM users
WHERE age > 18;
```

3. List users who are over the age of 18 and have the last name Barrows

```sql
SELECT * 
FROM users
WHERE age > 18 AND last_name = 'Barrows';
```

4. List users over the age of 18 who live in Canada sorted by age from oldest to youngest and then last name alphabetically 

```sql
SELECT * 
FROM users
WHERE age > 18 AND country = 'Canada'
ORDER BY age DESC, last_name;
```

5. List users who live in Canada and whose accounts are overdue

```sql
SELECT * 
FROM users
WHERE country = 'Canada' AND payment_due_date < '2020-06-22';

-- use the NOW() function to get the current date/time
SELECT *
FROM users
WHERE country = 'Canada' AND payment_due_date < NOW();
```

6. List all the countries users live in; don't repeat any countries

```sql
SELECT country, COUNT(country)
FROM users
GROUP BY country
ORDER BY country;
```

For the rest of the queries, we'll be using the `albums` and `songs` tables.

![albums and songs](https://andydlindsay-portfolio.s3.amazonaws.com/lighthouse/albums-and-songs.png)

7. List all albums along with their songs

```sql

```
8. List all albums along with how many songs each album has

```sql

```

9. Enhance previous query to only include albums that have more than 10 songs

```sql

```

10. List ALL albums in the database, along with their songs if any

```sql

```

11. List albums along with average song rating

```sql

```

12. List albums and songs with rating higher than album average

```sql

```

### Useful Links
- [Top 10 Most Popular RDBMSs](https://www.c-sharpcorner.com/article/what-are-the-most-popular-relational-databases/)
- [Another Ranking of DBMSs](https://db-engines.com/en/ranking)
- [SELECT Queries Order of Execution](https://sqlbolt.com/lesson/select_queries_order_of_execution)
- [SQL Joins Visualizer](https://sql-joins.leopard.in.ua/)
