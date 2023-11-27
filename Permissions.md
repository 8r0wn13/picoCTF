# Permissions

## Description
This write up will show how to solve the CTF for "Permissions"

## Solution
`sudo -l` will show to what the user `picoplayer` has access to.</br>
One of the things `picoplayer` has access to is to `vi`.</br>
To open the `/root` folder `sudo vi /root` and it will list some files.</br>
Select `flag.txt`.
