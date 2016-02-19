---
published: true
layout: post
title: "Dive into Sqlite"
author: Boy Sandy Gladies Arriezona
categories: programming
tags:
    - python
    - sqlite
comments: True
---

## Introduction

Today we will talk about sqlite in python. I often use mysql as my data source because of a habit, but when I am in a hurry, I guess sqlite will be enough.

#### To keep in mind:

- I use python3
- Sqlite library is called sqlite3
- I use hashlib to hash the password (not required)

## Action

Let's start with a little bit of code:

``` python
#!/usr/bin/python
# -*- coding: utf-8 -*-

import hashlib
import sqlite3


con = sqlite3.connect('test.db')
```

You can see what I'm talking about before. Those import statement is where put all required libraries. The *con* variable will handle the connection from / into sqlite database which named "test.db". Don't mind the space between import and con, it's just a habit to give 2 empty line between import statement and code below it.

``` python
with con:
	con.row_factory = sqlite3.Row  # this one
	cur = con.cursor()
```

Now, "this one" is what I prefer because we will get a dictionary when we select some data from sqlite. We can ignore it of course, but the result from our query will be tuple which I do not prefer.
"with" statement will handle the resource and exception. We can also handle the resource manually (close the connection) and use try-except to handle the exception.

``` python
print(data[0], data[1], ..., data[n])
```
People will not understand what we print unless we tell them.

``` python
print(data['id'], data['email'], data['username'], ...)
```
This one will be more understandable.

This is a little code to show how we drop or create table and insert some data into sqlite.

``` python
cur.execute("DROP TABLE IF EXISTS users")
cur.execute("CREATE TABLE users (id, email, username, password, authenticated)")
cur.execute("INSERT INTO users VALUES (?, ?, ?, ?, ?)", [1, "petruk@gmail.com", "petruk", hashlib.md5("passwordpetruk".encode()).hexdigest(), True])

cur.execute("SELECT * FROM users WHERE id=?", (1,))
datum = cur.fetchone()
print("{} {} {} {} {}".format(datum['id'], datum['email'], datum['username'], datum['password'], datum['authenticated']))
```

Some explanation
- We drop the table first if the table is exist
- We create new table which named *users*. It has several field which is *id*, *email*, *username*, *password*, and *authenticated*.
- We insert a new user into users table.
- We find a user with a specified id.

#### To keep in mind:

> I use parameterized queries to insert data. Look for it, it will be helpful for your project. 
> I also use hashlib to hash the password. In real case, you should use a better security like bcrypt or others.

Now, you can see why I use that *row_factory*. The next code will show you how to do batch insert with sqlite. Instead of *execute*, we can use *executemany* to insert data.

``` python
wayang_actors = (
	(2, "gareng@gmail.com", "gareng", hashlib.md5("passwordgareng".encode()).hexdigest(), True),
	(3, "bagong@gmail.com", "bagong", hashlib.md5("passwordbagong".encode()).hexdigest(), True)
)
cur.executemany("INSERT INTO users VALUES (?, ?, ?, ?, ?)", wayang_actors)

cur.execute("SELECT * FROM users")
data = cur.fetchall()
for datum in data:
	print("{} {} {} {} {}".format(datum['id'], datum['email'], datum['username'], datum['password'], datum['authenticated']))
```

Now this one is the update query.

``` python
cur.execute("UPDATE USERS SET email=? WHERE id=?", ("goreng@gmail.com", 2))
print("Data updated: {}".format(cur.rowcount))

cur.execute("SELECT * FROM users")
data = cur.fetchall()
for datum in data:
	print("{} {} {} {} {}".format(datum['id'], datum['email'], datum['username'], datum['password'], datum['authenticated']))
```

The completed code is this one.

``` python
#!/usr/bin/python
# -*- coding: utf-8 -*-

import hashlib
import sqlite3


con = sqlite3.connect('test.db')

with con:
	con.row_factory = sqlite3.Row
	cur = con.cursor()    

	print("# drop, create table and insert example")
	cur.execute("DROP TABLE IF EXISTS users")
	cur.execute("CREATE TABLE users (id, email, username, password, authenticated)")
	cur.execute("INSERT INTO users VALUES (?, ?, ?, ?, ?)", [1, "petruk@gmail.com", "petruk", hashlib.md5("passwordpetruk".encode()).hexdigest(), True])

	cur.execute("SELECT * FROM users WHERE id=?", (1,))
	datum = cur.fetchone()
	print("{} {} {} {} {}".format(datum['id'], datum['email'], datum['username'], datum['password'], datum['authenticated']))
	print()

	print("# batch insert example")
	wayang_actors = (
		(2, "gareng@gmail.com", "gareng", hashlib.md5("passwordgareng".encode()).hexdigest(), True),
		(3, "bagong@gmail.com", "bagong", hashlib.md5("passwordbagong".encode()).hexdigest(), True)
	)
	cur.executemany("INSERT INTO users VALUES (?, ?, ?, ?, ?)", wayang_actors)

	cur.execute("SELECT * FROM users")
	data = cur.fetchall()
	for datum in data:
		print("{} {} {} {} {}".format(datum['id'], datum['email'], datum['username'], datum['password'], datum['authenticated']))
	print()

	print("# update example")
	cur.execute("UPDATE USERS SET email=? WHERE id=?", ("goreng@gmail.com", 2))
	print("Data updated: {}".format(cur.rowcount))

	cur.execute("SELECT * FROM users")
	data = cur.fetchall()
	for datum in data:
		print("{} {} {} {} {}".format(datum['id'], datum['email'], datum['username'], datum['password'], datum['authenticated']))
	print()
```

Thank you, I hope it will help.