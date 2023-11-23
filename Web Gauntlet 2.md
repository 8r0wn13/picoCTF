# Web Gauntlet 2

## Description
This write up will show how to solve the CTF for "Web Gauntlet 2"

## Solution
It is mentioned that it is an sqlite database.</br>
/filter.php shows which characters are not allowed, including `admin`.</br>
In sqlite `||` is concatenating strings in the database, hence we can use `ad'||'min.</br>
In order to get the password, we can use the `glob` function: `' glob '*`</br>
Logging in with `ad'||'min:' glob '*` is successful and will mention to go to `/filter.php` where the flag will be revealed.</br>
