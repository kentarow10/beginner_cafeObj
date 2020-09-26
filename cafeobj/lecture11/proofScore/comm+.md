## Theorem 2 [Commutativity of _+_ (comm+)]

X + Y = Y + X

#### Lemma 1 [Right zero of _+_ (rz+)]

X + 0 = X

Proof of Lemma 1 By structural induction on X

I. Base case

```
open PNAT1 .
-- check
red 0 + 0 = 0 .
close
```

II. Induction case

```
open PNAT1 .
-- fresh constants
op x : -> PNat .
-- IH
eq x + 0 = x .
-- check
red s(x) + 0 = s(x) .
close
```

End of Proof of Lemma 1

#### Lemma 2 [Right successor of _+_ (rs+)]

X + s(Y) = s(X + Y)

Proof of Lemma 2 By structural induction on X.

I. Base case

```
open PNAT1 .
-- fresh constants
op y : -> PNat .
-- check
red 0 + s(y) = s(0 + y) .
close
```

II. Induction case

```
open PNAT1 .
-- fresh constants
ops x y : -> PNat .
-- IH
eq x + s(y) = s(x + y) .
-- check
red s(x) + s(y) = s(s(x) + y) .
close
```
End of Proof of Lemma 2

* Proof of Theorem 2 By structural induction on X.

I. Base case

```
open PNAT1 .
-- fresh constants
op y : -> PNat .
-- lemmas
eq X + 0 = X . -- (rz+)
-- check
red 0 + y = y + 0 .
close
```

II. Induction case

```
open PNAT1 .
-- fresh constants
ops x y : -> PNat .
-- lemmas
eq X + s(Y) = s(X + Y) . -- (rs+)
-- IH
eq x + Y = Y + x .
-- check
red s(x) + y = y + s(x) .
close
```

End of Proof of Theorem 2


