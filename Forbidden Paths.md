# Forbidden Paths

## Description
This write up will show how to solve the CTF for "Forbidden Paths"

## Solution
The exercise shows where the web application is living and where `flag.txt` is located.
Entering `/flag.txt` is not going to work, as absolute path traversal is not allowed.</br>
Entering `../../../../../flag.txt` is relative path traversal and will show the flag.
