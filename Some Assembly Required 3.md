# Some Assembly Required 1

## Description
This write up will show how to solve the CTF for "Some Assembly Required 1"

## Solution
Deobfuscate the JavaScript file with Obfuscator.io.</br>
After deobfuscating, it shows a file `qCCYI0ajpD`.</br>
Downloading the file: `wget http://mercury.picoctf.net:56800/qCCYI0ajpD -q -O script.wasm`</br>
Convert the file to a `wat` file: `wasm2wat --generate-names script.wasm > script.wat`
At the end of the file, it shows hexdecimal values.</br>

<< I am lost >>
