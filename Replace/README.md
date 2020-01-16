# Replace

Executing `Replace.exe` and entering random integers crashes the program. After
tracing in the debugger, we can find out that at there is some self modifying
code, and at `0040466F`, there is an out-of-bounds assignment that causes the
program to crash. Upon further debugging, we see that it assigns the value
`0x90` to the address stored in `eax`, and that address is equal to
`input + 601605CC` (32-bit int). Furthermore, the code that outputs `Correct!`
will never be executed since there is a `jmp` before it at `00401071`.
Therefore, we can calculate the input such that the assignment will modify the
`jmp` at `00401071` into `0x90`, which is `nop`, and `Correct!` will be output.
The calculated address, `2687109798`, is thus the flag.
