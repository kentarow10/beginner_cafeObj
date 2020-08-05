## Theorem 3 [Correctness of a reverse of reverse (revrev)]

rev1(rev1(L1)) = L1

#### Lemma 1

rev1(L1 @ L2) = rev1(L2) @ rev1(L1)

Proof of Lemma 1 By structural induction on L1

I. Base case

```
open LIST2 .
op l2 : -> List .
-- check
red rev1(nil @ l2) = rev1(l2) @ rev1(nil)
close
```

II. Induction case

```
open LIST3 .
-- fresh constants
ops l1 l2 : -> List .
ops e e2 : -> Elt.E .
-- induction hypothesis
eq rev1(L1 @ L2) = rev1(L2) @ rev1(L1) .
-- check
red rev1((e | l1) @ l2) = rev1(l2) @ rev1(e | l1)
close
```

End of Proof of Lemma 1


Proof of Theorem 3 By structural induction on L1

I. Base case

```
open LIST3 .
-- check
red rev1(rev1(nil)) = nil .
close
```

II. Induction case

```
open LIST3 .
-- fresh constants
ops l1 l2 : -> List .
ops e e2 : -> Elt.E .
-- induction hypothesis
eq rev1(rev1(L1)) = L1 .
-- lemmas
eq rev1(L1 @ L2) = rev1(L2) @ rev1(L1) .
-- check
red rev1(rev1(e | l1)) = e | l1 .
close
```

End of Proof of Theorem 3