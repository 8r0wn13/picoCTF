# Power Cookie

## Description
This write up will show how to solve the CTF for "Power Cookie"

## Solution
Going to the website, there is button to `Continue as guest`</br>
Clicking on the button, will bring you forward, but it only shows a message.</br>
Opening `Storage > Cookies`, there is an `isAdmin` cookie, set to zero.</br>
Setting the value to `1` and refreshing the page, will show the flag.
