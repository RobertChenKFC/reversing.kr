# CSHOP

Opening with IDA, we can see that `CSHOP.exe` is a .NET assembly. Therefore, I
decompiled it with dotPeek and find out that the function `FrmMain._Click`
seems the assign some strings to some labels. Since clicking on the window does
nothing, I pressed the spacebar instead and got the flag `P4W6RP6SES`.
