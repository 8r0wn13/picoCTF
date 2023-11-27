# Some Assembly Required 2

## Description
This write up will show how to solve the CTF for "Some Assembly Required 2"

## Solution
Looking at the JavaScript, there is an obfuscated file `aD8SvhyVkb`.</br>
Downloading the file: `wget http://mercury.picoctf.net:23889/aD8SvhyVkb -q -O script.wasm`
Using strings to see what the file says: `strings script.wasm`
```
memory
__wasm_call_ctors
strcmp
check_flag
input
	copy_char
__dso_handle
__data_end
__global_base
__heap_base
__memory_base
__table_base
j!	 
  F!!A
!" ! "q!# #
!% $ %q!& 
!( ' (q!) & )k!* 
!+ +
 	q!
+xakgK\Nsl<8?nmi:<i;0j9:;?nm8i=0??:=njn=9u
```
Putting this in Cyberchef.io, with Magic and `Intensive Mode` on, it gives the flag.</br>
It uses `XOR` with a `8 key`.
