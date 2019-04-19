# PSQL Returning

### 04/19/2019


Normally when you insert a record in postgres, the query returns something like the following:

```sql
insert into users(email) values ('john@test.com') returning *;
INSERT 0 1
```


You get a preview of the objects inserted by using the `returning` keyword.

```sql
insert into users(email) values ('john@test.com') returning *;
     email
---------------
 john@test.com
(1 row)

INSERT 0 1
```

H/T Mary Lee for showing this off on a Friday Show and Tell

Tags: psql, Returning, PostgreSQL
