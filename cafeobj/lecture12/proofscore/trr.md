## Theorem 2 [Correctness of a tail recursive reverse (ctrr)]

rev1(L1) = rev2(L1)

#### Lemma 1 [A property of sr2 (p-sr2)]

sr2(L1,E2 | L2) = sr2(L1,nil) @ (E2 | L2)

Proof of Lemma 1 By structural induction on L1.

I. Base case

```
open LIST2 .
-- fresh constants
op l2 : -> List .
op e2 : -> Elt.E .
-- check
red sr2(nil,e2 | l2) = sr2(nil,nil) @ (e2 | l2) .
close
```

II. Induction case

```
open LIST2 .
-- fresh constants
ops l1 l2 : -> List .
ops e e2 : -> Elt.E .
-- induction hypothesis
eq sr2(l1,E2 | L2) = sr2(l1,nil) @ (E2 | L2) .
-- check
red sr2(e | l1,e2 | l2) = sr2(e | l1,nil) @ (e2 | l2) .
close
```

Proof of Theorem 2 By structural induction on L1

I. Base case

```
open LIST2 .
-- check
red rev1(nil) = rev2(nil) .
close
```

II. Induction case

```
open LIST2 .
-- fresh constants
op l1 : -> List .
op e : -> Elt.E .
-- induction hypothesis
eq rev1(l1) = rev2(l1) .
-- lemmas
eq sr2(L1,E2 | L2) = sr2(L1,nil) @ (E2 | L2) .
-- check
red rev1(e | l1) = rev2(e | l1) .
close
```

End of Proof of Theorem 2

