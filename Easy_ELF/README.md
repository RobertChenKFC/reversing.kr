# Easy ELF

Decompiling with IDA, we can see that the `input` is checked in the function
`sub_8048451`, where it xors `input[0]`, `input[2]`, `input[3]` with `0x34`,
`0x32`, `0x88` respectively, and check if the string equals `"x1|\xDDX"`.
Therefore, I wrote a simple script to xor the bytes back and obtained the flag
`L1NUX`.
