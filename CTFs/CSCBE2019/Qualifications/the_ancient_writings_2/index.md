# Ancient Writings #2

### [~$ cd ..](../)

Author: [Renaud11232](https://renaud11232.github.io)

To solve this challenge we were given two text files with a `.bf` extension and were asked to provide the missing line of code that would fit between the to files to make the program give the same output as [Ancient Writings #1](../ancient_writings_1).
Once we had found that line, we had submit it with to a given site that will give us the flag:

```
>232+*""43*52**5+65+:*4::**3:*21+:** "b"$                 v    >
^"78"v $  $ \ $ \ $<"x32P"    _                           "    v
^|%24<"SC{key_Y3ByZXNzZXk=}"  ^7        *:+33 +*27*7 *44"key"  <
<>47+:*1+                                     47+:*2+v    "   >^
```
```
>                                        >    34*9g"SC":vv     ^
<                                                    v:,_@>"#_"^
>                                                    >  ^      <

0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZv^<>0123456789abcdefghijklmnopqrstuvwxyz
```

The code of this challenge and the one from the previous challenge were very similar. And the corresponding line in the previous snippet was :

```
>v                                                       <<    ^<
```

Once we understood using our good old friend Google, that `<`, `>`, `^` and `v` were arrows directing the code execution in 2D, we simply had to align those arrows with the new code.

```
>232+*""43*52**5+65+:*4::**3:*21+:** "b"$                 v    >
^"78"v $  $ \ $ \ $<"x32P"    _                           "    v
^|%24<"SC{key_Y3ByZXNzZXk=}"  ^7        *:+33 +*27*7 *44"key"  <
<>47+:*1+                                     47+:*2+v    "   >^
v                                                    <        ^<
>                                        >    34*9g"SC":vv     ^
<                                                    v:,_@>"#_"^
>                                                    >  ^      <

0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZv^<>0123456789abcdefghijklmnopqrstuvwxyz
```

So the needed line is :

```
v                                                    <        ^<
```

Once submitted we were greeted with a warm
```
CSC{#d^wv<>e23$&@dDHC}
```

DONE