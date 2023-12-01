# Irish-Name-Repo 1

## Description
This write up will show how to solve the CTF for "Irish-Name-Repo 1"

## Solution
Checking the login page and trying to log in with a default sqli: `admin' OR 1=1;--` is not working and stating sqli is detected.</br>
When inspecting the source code, it seems there is a hidden field `debug`.</br>
Remove the word `hidden`, changing the value to `1` and trying the same payload `admin' OR 1=1;--` will give the same message, but it will also state the query for debugging purposes.</br>
