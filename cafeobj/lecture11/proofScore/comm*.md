## Theorem 4 [Commutativity of _*_ (comm*)]

X * Y = Y * X

#### Lemma 4 [Right zero of _*_ (rz*)]

X * 0 = 0

Proof of Lemma 4 By structural induction on X.

I. Base case

```
open PNAT2 .
-- check
red 0 * 0 = 0 .
close
```

II. Induction case

```
open PNAT2 .
-- fresh constants
op x : -> PNat .
-- IH
eq x * 0 = 0 .
-- check
red s(x) * 0 = 0 .
close
```

End of Proof of Lemma 4

#### Lemma 5 [Right successor of _*_ (rs*)]

X * s(Y) = (X * Y) + X

I. Base case

```
open PNAT2 .
-- fresh constants
op y : -> PNat .
-- check
red 0 * s(y) = (0 * y) + 0 .
close
```

II. Induction case

```
open PNAT2 .
-- fresh constants
ops x y : -> PNat .
-- IH
eq x * s(Y) = (x * Y) + x .
-- check
red s(x) * s(y) = (s(x) * y) + s(x) .
close
```

End of Proof of Lemma 5

* Proof of Theorem 4 By structural induction on X.

I. Base case 

```
open PNAT2 .
-- fresh constants
op y : -> PNat .
-- lemmas
eq X * 0 = 0 . -- (rz*)
-- check
red 0 * y = y * 0 .
close
```

II. Induction case

```
open PNAT2 .
-- fresh constants
ops x y : -> PNat .
-- lemmas
eq X * s(Y) = (X * Y) + X . -- (rs*)
-- IH
eq x * Y = Y * x .
-- check
red s(x) * y = y * s(x) .
close
```

End of Proof of Theorem 4
