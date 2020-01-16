# ImagePrc

Executing `ImagePrc.exe`, we can see that there is a canvas where we can draw
something, and there is a `Check` button to see if we have drawn correctly.
Decompiling with IDA, we can see that the input bitmap is directly compared
with a buffer at `0047e060`, and from other pieces of code, we can see that the
bitmap has size `250x150` (3 channel), which is `90000` bytes. So, I debugged
the program and dumped the content of the buffer into a file, and wrote a
simple script to display it, which obtained the flag `GOT`.
