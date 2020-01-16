# Easy Crack
Decompiling with IDA, we can see that the input `string` is checked in the
function `sub_401080`, and the function only prints `Congratulation !!` if
`str[0] == 'E'`, `str[1] == 'a'` , `strncmp(str + 2, "5y", 2) == 0` and
`strcmp(str + 4, "R3versing") == 0`, thus the flag is `Ea5yR3versing`.
