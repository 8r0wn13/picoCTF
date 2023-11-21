# findme

## Description
This write up will show how to solve the CTF for "findme"

## Solution 1st flag
On the page, login with the credentials given: `test:test!`.</br>
Checking the source code and the responses, after logging in, the page is redirected twice with a page id, which looks like base64 encoded: `cGljb0NURntwcm94aWVzX2Fs` and `bF90aGVfd2F5X2RmNDRjOTRjfQ`.</br>
Decoding each of them, seems like half of the flag, combining them both together, gives the flag.</br>
`echo -n "cGljb0NURntwcm94aWVzX2FsbF90aGVfd2F5X2RmNDRjOTRjfQ" | base64 -d`
