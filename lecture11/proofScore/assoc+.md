## Theorem 1 [associativity of _+_ (assoc+)]

(X + Y) + Z = X + (Y + Z)

Proof of Theorem 1. By structural induction on X.

I. Base case

```
open PNAT1 .
-- fresh constants
ops y z : -> PNat .
-- check
red (0 + y) + z = 0 + (y + z) .
close
```

II. Induction case

```
open PNAT1 .
-- fresh constants
ops x y z : -> PNat .
-- IH
eq (x + Y) + Z = x + (Y + Z) .
-- check
red (s(x) + y) + z = s(x) + (y + z) .
close
```

End of Proof of Theorem 1