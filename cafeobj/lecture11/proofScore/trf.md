## Theorem 5 [Correctness of a Tail Recursive Factorial (trf)] 

fact1(X) = fact2(X)

#### Lemma 6 [Property of sfact2 (p‐sf2)]

Y * sfact2(X,Z) = sfact2(X,Y * Z)

Proof of Lemma 6 By structural induction on X.

I. Base case

```
open PNAT3 .
-- fresh constants
ops y z : -> PNat .
-- check
red y * sfact2(0,z)
= sfact2(0,y * z) .
close
```

II. Induction case

```
open PNAT3 .
-- fresh constants
ops x y z : -> PNat .
-- lemmas
eq (X + Y) * Z = (X * Z) + (Y * Z) . -- (d*o+)
-- IH
eq Y * sfact2(x,Z) = sfact2(x,Y * Z) .
-- check
red y * sfact2(s(x),z) = sfact2(s(x),y * z) .
close
```

End of Proof of Lemma 6

* Proof of Theorem 5 By structural induction on X.

I. Base case

```
open PNAT3 .
-- check
red fact1(0) = fact2(0) .
close
```

II. Induction case

```
open PNAT3 .
-- fresh constants
op x : -> PNat .
-- lemmas
eq Y * sfact2(X,Z) = sfact2(X,Y * Z) . -- (sf2-p)
-- IH
eq fact1(x) = fact2(x) .
-- check
red fact1(s(x)) = fact2(s(x)) .
close
```

End of Proof of Theorem 5
