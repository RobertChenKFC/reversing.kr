# Easy Keygen

The goal is to find the correct `name` for the `serial` to be
`5B134977135E7D13`. Decompiling with IDA, we can see that `main` reads `name`
as a string but `serial` as hex, and every `name[i]` is first xored with
`arr[i % 3]` where `arr[] = {16, 32, 48}`, then compared with `serial`.
So I wrote a simple script to take the `serial` and xor the bytes back to the
name, and we obtain the flag `K3yg3nm3`.
