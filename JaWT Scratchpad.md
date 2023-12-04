# JaWT Scratchpad

## Description
This write up will show how to solve the CTF for "JaWT Scratchpad"

## Solution
When going to the web page, we can enter a name, but not the user `admin`</br>
Creating a name, it will generate a jwt-token.</br>
Using jwt.io, it shows the following:</br>
```
{
  "typ": "JWT",
  "alg": "HS256"
}
{
  "user": "user"
}
```

Changing the `admin` will not work, as there is a secret key.</br>
With John the Ripper, this might be able to be retrieved: `john jwt.txt --format=HMAC-SHA256 --wordlist=rockyou.txt`

The secret key will be: `ilovepico`</br>

Creating a new token on jwt.io, by changing `user` to `admin` and adding the secret key, will give the following jwt-token:</br>
`eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiYWRtaW4ifQ.gtqDl4jVDvNbEe_JYEZTN19Vx6X9NNZtRVbKPBkhO-s`</br>

When changing the cookie in the browser and refreshing the page, it will show the flag.
