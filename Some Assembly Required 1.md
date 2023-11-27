# Some Assembly Required 1

## Description
This write up will show how to solve the CTF for "Some Assembly Required 1"

## Solution
There is a JavaScript file, which is quite unreadable, however, on the top, in the first array, there is `./JIFxzHyW8W`.</br>
Downloading this with: `wget http://mercury.picoctf.net:37669/JIFxzHyW8W -q -O script.wasm` and cat the file `cat script.wasm` shows the flag at the end of the file.
Another solution, instead of `cat script.wasm` would be `strings script.wasm`
