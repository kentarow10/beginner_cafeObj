## Theorem 1 [(relative) correctness of the compiler with respect to the interpreter]

inter(E) = vm(comp(E))

#### Lemma 1

inter(EN) = vm(comp(EN))

Proof of Lemma 1 By structural induction on EN.

1. base case

```
open VERIFY-COMP .
red inter(0) = vm(comp(0)) .
close
```

2. induction case

```
open VERIFY-COMP .
op en : -> ExpPNat .
-- IH
eq inter(en) = vm(comp(en)) .
-- check
red inter(s(en)) = vm(comp(s(en))) .
close
```

End of Proof of Lemma 1

#### Lemma 2

exec(comp(E) @ L,S) = exec(L,vm(comp(E)) | S)

Proof of Lemma 2 By structural induction on E.

1. base case

```
open VERIFY-COMP .
op en : -> ExpPNat .
op l : -> IList .
op s : -> Stack .
red exec(comp(en) @ L,S) = exec(L,vm(comp(en)) | S) .
close
```

2. induction case

```
open VERIFY-COMP .
ops e1 e2 : -> Exp .
op l : -> IList .
op s : -> Stack .
-- IH
eq exec(comp(e1) @ L,S) = exec(L,vm(comp(e1)) | S) .
eq exec(comp(e2) @ L,S) = exec(L,vm(comp(e2)) | S) .
-- check
red exec(comp(e1 + e2) @ L,S) = exec(L,vm(comp(e1 + e2)) | S) .
red exec(comp(e1 - e2) @ L,S) = exec(L,vm(comp(e1 - e2)) | S) .
red exec(comp(e1 * e2) @ L,S) = exec(L,vm(comp(e1 * e2)) | S) .
red exec(comp(e1 / e2) @ L,S) = exec(L,vm(comp(e1 / e2)) | S) .
red exec(comp(e1 % e2) @ L,S) = exec(L,vm(comp(e1 % e2)) | S) .
close
```

End of Proof of Lemma 2

Proof of Theorem 1 By structural induction on E.

1. base case

```
open VERIFY-COMP .
-- fresh constants
op en : -> ExpPNat .
-- lemmas
eq inter(EN) = vm(comp(EN)) .
-- check
red th1(en) .
close
```

2. induction case

```
open VERIFY-COMP .
-- fresh constants
ops e1 e2 : -> Exp .
-- lemmas
eq exec(comp(E) @ L,S) = exec(L,vm(comp(E)) | S) .
-- induction hypothesis
eq inter(e1) = vm(comp(e1)) .
eq inter(e2) = vm(comp(e2)) .
-- check
red th1(e1 + e2) .
red th1(e1 - e2) .
red th1(e1 * e2) .
red th1(e1 / e2) .
red th1(e1 % e2) .
close
```

End of Proof of Theorem 1