# skills-api

Fake JSON Server using [my-json-server](https://my-json-server.typicode.com/)

## Entities (SQL-Model)

### Categories

```sql
CREATE TABLE categories (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  name TEXT NOT NULL,
);
```

### Skills

```sql
CREATE TABLE skills (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  name TEXT NOT NULL,
  description TEXT NOT NULL,
  icon_url TEXT,
  category_id INTEGER NOT NULL,
  FOREIGN KEY(categoryId) REFERENCES categories(id)
);
```

## Table representation

### Categories

| id  | name                  |
| --- | --------------------- |
| 1   | Programming Languages |
| 2   | Databases             |

### Skills

| id  | name       | description                                                                                                                                                                                                   | icon_url                                                                       | category_id |
| --- | ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | ----------- |
| 1   | Java       | Java is a general-purpose computer-programming language that is concurrent, class-based, object-oriented, and specifically designed to have as few implementation dependencies as possible.                   | https://upload.wikimedia.org/wikipedia/en/3/30/Java_programming_language_logo.svg | 1           |
| 2   | JavaScript | JavaScript, often abbreviated as JS, is a high-level, interpreted programming language. It is a language which is also characterized as dynamic, weakly typed, prototype-based and multi-paradigm.            | https://upload.wikimedia.org/wikipedia/commons/6/6a/JavaScript-logo.png           | 1           |
| 3   | SQL        | SQL is a domain-specific language used in programming and designed for managing data held in a relational database management system, or for stream processing in a relational data stream management system. | https://upload.wikimedia.org/wikipedia/commons/8/87/Sql_data_base_with_logo.png   | 2           |


## Available endpoints

API BASE URL: https://my-json-server.typicode.com/zenor27/skills-api

### Categories

| Method | URL           | Description          |
| ------ | ------------- | -------------------- |
| GET    | /categories   | Get all categories   |
| GET    | /categories/1 | Get category by id 1 |

### Skills
| Method | URL         | Description        |
| ------ | ----------- | ------------------ |
| GET    | /skills     | Get all skills     |
| GET    | /skills/1   | Get skill by id 1  |