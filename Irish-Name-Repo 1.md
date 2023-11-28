# Irish-Name-Repo 1

## Description
This write up will show how to solve the CTF for "Irish-Name-Repo 1"

## Solution
Clicking through the app, there is a Support page.</br>
There are few users making posts and the `Admin` is replying to the posts.</br>
This means there is an Admin user.</br>

When going to the admin login and try `Admin:admin`, we can see what is replied.</br>
It states Login has failed.</br>
Let's try a standard payload: `Admin' OR 1=1;--`</br>
This makes it possible to login and it will show the flag.
