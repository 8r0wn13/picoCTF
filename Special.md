# Special

## Description
This write up will show how to solve the CTF for "Special"

## Solution
Regular commands are not known, as the first letter is being capitalized.</br>
With `(())` we can go around that, i.e.: `((ls))`.</br>
It is not possible to add additional arguments, f.e. `((ls -la))`</br>
`((ls))` did show `blargh`, but `((cat blargh))` doesn't work as it doesn't accept second parameters.</br>
`((cat)) < blargh` turned out it is a directory.</br>
Guessing it will contain a `flag.txt` I tried `((cat)) < blargh/flag.txt` which returns the flag.
