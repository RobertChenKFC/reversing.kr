# Position

The goal is to find the correct `name` for the `serial` to be `76876-77776`.
Decompiling with IDA, we can see that the code seems to be written in C++, so
there are lots of constructor/destructor calls. Ignoring the unimportant ones,
we can see that the function `sub_401740` is the one that does the actual
comparison. Looking closely, we can see `name` and `serial` are of type
`CString`, `name` should be a string of length 4, and each byte of `name` has
some constraint. Going through all the code, we can conclude that:

- `(0,0) != (1,2)`
- `(0,3) == (1,3) == 0`
- `(0,1) == (1,4) == 1`
- `(0,2) != (1,0)`
- `(0,4) == (1,1) == 0`
- `(2,0) != (3,2)`
- `(2,3) != (3,3)`
- `(2,1) != (3,4)`
- `(2,2) != (3,0)`
- `(2,4) == (3,1) == 0`

where `(i,j) = (name[i] >> j) & 1` and `serial = "76876-77776"`.

Therefore, I wrote a simple script to brute force all printable ascii
characters and output the ones that satisfies the constraints, all of which
(I chose `bump`) are valid flags.
