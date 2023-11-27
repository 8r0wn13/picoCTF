# Roboto Sans
## Description
This write up will show how to solve the CTF for "Roboto Sans"

## Solution
As the title says Roboto, I tried `/robots.txt`.</br>
There are a few base64 encoded values:</br>
`ZmxhZzEudHh0;anMvbXlmaW`: `flag1.txtjs/myfi`
`anMvbXlmaWxlLnR4dA==`: `js/myfile.txt`
`svssshjweuiwl;oiho.bsvdaslejg`: decoded as gibberish

Trying the following endpoints:</br>
`/flag1.txt` results in a 404 - Not Found.</br>
`/js/myfile.txt` shows the flag.
