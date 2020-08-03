## Theorem 6 [Correctness of a Tail Recursive Sum (trs)] 

sum1(X) = sum2(X)

#### Lemma 6 [Property of ssum2 (p‐sf2)]

Y + ssum2(X,Z) = ssum2(X,Y + Z)

Proof of Lemma 6 By structural induction on X.

I. Base case

```
open PNAT3 .
-- fresh constants
ops y z : -> PNat .
-- check
red y + ssum2(0,z) = ssum2(0,y + z) .
close
```

II. Induction case

```
open PNAT3 .
-- fresh constants
ops x y z : -> PNat .
-- IH
eq Y + ssum2(x,Z) = ssum2(x,Y + Z) .
-- check
red y + ssum2(s(x),z) = ssum2(s(x),y + z) .
close
```

End of Proof of Lemma 6

* Proof of Theorem 5 By structural induction on X.

I. Base case

```
open PNAT3 .
-- check
red sum1(0) = sum2(0) .
close
```

II. Induction case

```
open PNAT3 .
-- fresh constants
op x : -> PNat .
-- lemmas
eq Y + ssum2(X,Z) = ssum2(X,Y + Z) .
-- IH
eq sum1(x) = sum2(x) .
-- check
red sum1(s(x)) = sum2(s(x)) .
close
```

End of Proof of Theorem 5
