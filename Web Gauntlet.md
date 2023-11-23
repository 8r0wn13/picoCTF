# Web Gauntlet

## Description
This write up will show how to solve the CTF for "Web Gauntlet"

## Solution
We're not allowed to use valid credentials.</br>
As it is sqlite, in Web Gauntlet we used `ad'||'min:' glob '*` to log in.</br>
This solution worked for the first 2 rounds, but there are 5 rounds to go.</br>
Another solution to get beyond the 3rd barrie is to use a different comment. Use `/*` instead of `--`:</br>
`ad'||'min'/*:test`</br>

For round 4, it is not allowed to use the word `admin`, hence we can break it up with '`ad'||'min'/*:test`</br>
For round 5, it is not allowed to use `UNION`, but we can use the same payload as this doesn't contain the `UNION`.</br>

Now refresh `/filter.php` and the flag is there.
