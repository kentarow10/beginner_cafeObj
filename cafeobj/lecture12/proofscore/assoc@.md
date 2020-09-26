## Theorem 1 [Associativity of _@_ (assoc@)]

(L1 @ L2) @ L3 = L1 @ (L2 @ L3)

Proof of Theorem 1 By structural induction on L1.

I. Base case

```
open LIST1 .
-- fresh constants
ops l2 l3 : -> List .
-- check
red (nil @ l2) @ l3 = nil @ (l2 @ l3) .
close
```

II. Induction case

```
open LIST1 .
-- fresh constants
ops l1 l2 l3 : -> List .
op e : -> Elt.E .
-- induction hypothesis
eq (l1 @ L2) @ L3 = l1 @ (L2 @ L3) .
-- check
red ((e | l1) @ l2) @ l3 = (e | l1) @ (l2 @ l3) .
close
```

End of Proof of Theorem 1