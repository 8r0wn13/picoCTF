# JAuth

## Description
This write up will show how to solve the CTF for "JAuth"

## Solution
Trying to log in with `test:Test123!` provides a token (JWT cookie).</br>

When this token is being encoded with base64, it shows the following:
```
{
  "typ": "JWT",
  "alg": "HS256"
}
Payload
{
  "auth": 1688308967209,
  "agent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/114.0",
  "role": "user",
  "iat": 1688308967
}
```

In a payload converter, change the algorithm with the drop down (NOT IN THE CODE ITSELF!!) and change `user` to `admin`.</br>
Copy the newly created token, replace the token in the browser and add a `.` at the end.</br>
This will change the login to an admin login and provides the flag.
