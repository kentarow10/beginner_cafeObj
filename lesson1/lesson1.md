1. Type each piece of programs in the slides as one file, feed it 
into CafeOBJ, and do some testing. Note that the extension of 
a file name in which CafeOBJ programs are written is .cafe, 
such as fact.cafe.
2. Explain in which way fact(5) is computed.
3. Explain in which way oedc‐fact(5) is computed.
4. Write two versions of programs computing the summation 
0+1+2+…+n for a given number n, where one corresponds to 
fact and the other corresponds to oedc-fact and do some 
testing for both versions.
5. Write a program in CafeoBJ that corresponds to the 
following and do some testing
```
ext-fib(n) =
0
1
2
ext-fib(n–1) + ext-fib(n–2)
+ ext-fib(n–3)
if n = 0
if n = 1
if n = 2
otherwise
```
The program should be such that sd is not used in it and when 
you use p t in it, t should be one or greater (namely that p t
should be a natural number). For example, let X be a variable 
of Nat, you are not allowed to use p X b/c X may be 0.
6. Revise the program in which the factorial function is 
defined such that instead of fact the following postfix 
operator is used:
op _! : Nat -> Nat .
7. Revise the program in which the odd‐even divide & 
conquer factorial function is defined such that instead of 
oedc-fact and cond the following postfix and mix‐fix operators 
are used:
op _! : Nat -> Nat .
op if_then {_} else {_} : Bool Nat Nat -> Nat .