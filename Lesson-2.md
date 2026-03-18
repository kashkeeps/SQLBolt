# Movies Table - SQL Exercises

## Table: movies

| id | title | director | year | length_minutes |
|----|-------|----------|------|----------------|
| 1 | Toy Story | John Lasseter | 1995 | 81 |
| 2 | A Bug's Life | John Lasseter | 1998 | 95 |
| 3 | Toy Story 2 | John Lasseter | 1999 | 93 |
| 4 | Monsters, Inc. | Pete Docter | 2001 | 92 |
| 5 | Finding Nemo | Andrew Stanton | 2003 | 107 |
| 6 | The Incredibles | Brad Bird | 2004 | 116 |
| 7 | Cars | John Lasseter | 2006 | 117 |
| 8 | Ratatouille | Brad Bird | 2007 | 115 |
| 9 | WALL-E | Andrew Stanton | 2008 | 104 |
| 10 | Up | Pete Docter | 2009 | 101 |
| 11 | Toy Story 3 | Lee Unkrich | 2010 | 103 |
| 12 | Cars 2 | John Lasseter | 2011 | 120 |
| 13 | Brave | Brenda Chapman | 2012 | 102 |
| 14 | Monsters University | Dan Scanlon | 2013 | 110 |

---

## Exercise 1: Find the movie with a row `id` of 6

```sql
SELECT * FROM movies
WHERE id = 6;
```

**Result:**

| id | title | director | year | length_minutes |
|----|-------|----------|------|----------------|
| 6 | The Incredibles | Brad Bird | 2004 | 116 |

**Explanation:**
- `WHERE id = 6` filters the table to return only the row where the `id` column equals `6`, which gives us **The Incredibles**.

---

## Exercise 2: Find the movies released in the `year`s between 2000 and 2010

```sql
SELECT * FROM movies
WHERE year BETWEEN 2000 AND 2010;
```

**Result:**

| id | title | director | year | length_minutes |
|----|-------|----------|------|----------------|
| 4 | Monsters, Inc. | Pete Docter | 2001 | 92 |
| 5 | Finding Nemo | Andrew Stanton | 2003 | 107 |
| 6 | The Incredibles | Brad Bird | 2004 | 116 |
| 7 | Cars | John Lasseter | 2006 | 117 |
| 8 | Ratatouille | Brad Bird | 2007 | 115 |
| 9 | WALL-E | Andrew Stanton | 2008 | 104 |
| 10 | Up | Pete Docter | 2009 | 101 |
| 11 | Toy Story 3 | Lee Unkrich | 2010 | 103 |

**Explanation:**
- `BETWEEN 2000 AND 2010` is an inclusive range filter, meaning it includes both **2000 and 2010** as valid values.
- It's a cleaner alternative to writing `WHERE year >= 2000 AND year <= 2010`, but both approaches return the same result.

---

## Exercise 3: Find the movies NOT released in the `year`s between 2000 and 2010

```sql
SELECT * FROM movies
WHERE year NOT BETWEEN 2000 AND 2010;
```

**Result:**

| id | title | director | year | length_minutes |
|----|-------|----------|------|----------------|
| 1 | Toy Story | John Lasseter | 1995 | 81 |
| 2 | A Bug's Life | John Lasseter | 1998 | 95 |
| 3 | Toy Story 2 | John Lasseter | 1999 | 93 |
| 12 | Cars 2 | John Lasseter | 2011 | 120 |
| 13 | Brave | Brenda Chapman | 2012 | 102 |
| 14 | Monsters University | Dan Scanlon | 2013 | 110 |

**Explanation:**
- `NOT BETWEEN 2000 AND 2010` is the inverse of `BETWEEN`, returning all rows where the year falls **outside** the range of 2000 to 2010.
- It excludes both endpoints, so movies from **1999 and earlier** or **2011 and later** are returned.
- It's equivalent to writing `WHERE year < 2000 OR year > 2010`.

---

## Exercise 4: Find the first 5 Pixar movies and their release `year`

```sql
SELECT title, year FROM movies
LIMIT 5;
```

**Result:**

| title | year |
|-------|------|
| Toy Story | 1995 |
| A Bug's Life | 1998 |
| Toy Story 2 | 1999 |
| Monsters, Inc. | 2001 |
| Finding Nemo | 2003 |

