# Client-side-again

## Description
This write up will show how to solve the CTF for "Client-side-again"

## Solution
The page doesn't show much, just an input to insert credential.</br>
Inspecting the code, it seems there is a `md5.js`.</br>
The `md5.js` file shows the flag in pieces: `37115`, `_again_3`, `picoCTF{` and `not_this`, making: `picoCTF{not_this_again_337115}`.
