# Movies Table - WHERE Clause Exercises

## Reference: Select Query with Constraints
```sql
SELECT column, another_column, …
FROM mytable
WHERE condition
    AND/OR another_condition
    AND/OR …;
```

---

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
| 87 | WALL-G | Brenda Chapman | 2042 | 97 |

---

## Exercise 1: Find all the Toy Story movies

```sql
SELECT * FROM movies
WHERE title LIKE 'Toy Story%';
```

**Result:**

| id | title | director | year | length_minutes |
|----|-------|----------|------|----------------|
| 1 | Toy Story | John Lasseter | 1995 | 81 |
| 3 | Toy Story 2 | John Lasseter | 1999 | 93 |
| 11 | Toy Story 3 | Lee Unkrich | 2010 | 103 |

**Explanation:**
- `LIKE 'Toy Story%'` matches any title that **starts with** "Toy Story", the `%` is a wildcard for anything that follows.

---

## Exercise 2: Find all the movies directed by John Lasseter

```sql
SELECT * FROM movies
WHERE director = 'John Lasseter';
```

**Result:**

| id | title | director | year | length_minutes |
|----|-------|----------|------|----------------|
| 1 | Toy Story | John Lasseter | 1995 | 81 |
| 2 | A Bug's Life | John Lasseter | 1998 | 95 |
| 3 | Toy Story 2 | John Lasseter | 1999 | 93 |
| 7 | Cars | John Lasseter | 2006 | 117 |
| 12 | Cars 2 | John Lasseter | 2011 | 120 |

**Explanation:**
- `= 'John Lasseter'` does an **exact match** on the director column.

---

## Exercise 3: Find all the movies (and director) not directed by John Lasseter

```sql
SELECT title, director FROM movies
WHERE director != 'John Lasseter';
```

**Result:**

| title | director |
|-------|----------|
| Monsters, Inc. | Pete Docter |
| Finding Nemo | Andrew Stanton |
| The Incredibles | Brad Bird |
| Ratatouille | Brad Bird |
| WALL-E | Andrew Stanton |
| Up | Pete Docter |
| Toy Story 3 | Lee Unkrich |
| Brave | Brenda Chapman |
| Monsters University | Dan Scanlon |
| WALL-G | Brenda Chapman |

**Explanation:**
- `!=` is the **not equal** operator, filtering out all rows where the director is John Lasseter.
- Only `title` and `director` columns are selected as the question asks for movies **and their director**.

---

## Exercise 4: Find all the WALL-* movies

```sql
SELECT * FROM movies
WHERE title LIKE 'WALL-%';
```

**Result:**

| id | title | director | year | length_minutes |
|----|-------|----------|------|----------------|
| 9 | WALL-E | Andrew Stanton | 2008 | 104 |
| 87 | WALL-G | Brenda Chapman | 2042 | 97 |

