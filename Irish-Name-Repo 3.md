# Irish-Name-Repo 3

## Description
This write up will show how to solve the CTF for "Irish-Name-Repo 3"

## Solution
There is only room for a password.</br>
In the source code is however a hidden field `debug`.</br>
Setting this to `1`, will show the query which is being executed on the database.</br>

When entering a password, it is encrypted, which turned out to be ROT13.</br>
Converting `' glob' *` to ROT13, will be: `' tybo '*`.</br>
Entering this password will show the flag.
