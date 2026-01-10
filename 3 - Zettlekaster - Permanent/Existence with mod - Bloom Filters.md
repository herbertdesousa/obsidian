Date: 2025-07-08
Tags: [[alternatives tricks]]

In a case that you need to check existence in your application, you can use redis to cache information and then go find the database... or:

1. In a given list:
[1:0, 2:0, 3:0, 4:0, 5:0, 6:0, 7:0]
About: [left position:right bit]

2. Inserting a new value, go mod the value:
Hash(Jonh) % 7 = 1
7 = Size of the list
1 = Position in the list

3. Mark this place at list as true:
[1:0, 2:0, 3:0, 4:0, 5:0, 6:0, 7:1]

4. Now, when a query looks for the data, it goes to the hash map, if it founds, goes to the database, otherwise not.

I may have collisions, so the database is source of the true.