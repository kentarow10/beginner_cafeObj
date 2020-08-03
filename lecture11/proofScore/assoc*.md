Theorem 3 [Associativity of _*_ (assoc*)]

(X * Y) * Z = X * (Y * Z)

Proof of Theorem 3 By structural induction on X.

I. Base case

open PNAT2 .
-- fresh constants
ops y z : -> PNat .
-- check
red (0 + y) * z = (0 * z) + (y * z) .
close

II. Induction case

open PNAT2 .
-- fresh constants
ops x y z : -> PNat .
-- IH
eq (x + Y) * Z = (x * Z) + (Y * Z) .
-- check
red (s(x) + y) * z = (s(x) * z) + (y * z) .
close

End of Proof of Theorem 3