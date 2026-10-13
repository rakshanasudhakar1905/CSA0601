# Task 7 – Solve the Recurrence

Use the iteration method for T(n) = T(n/2) + c, with T(1) = d.

T(n) = T(n/2) + c
     = T(n/4) + 2c
     = T(n/8) + 3c
     = T(n/2^k) + kc

Stop when n/2^k ≈ 1:
n/2^k ≈ 1
2^k ≈ n
k ≈ log₂(n)

Substitute k:
T(n) = T(1) + c log₂(n)
     = d + c log₂(n)

Thus T(n) = Θ(log n).

The method applies because each recursive call reduces the input size by about half and performs constant non-recursive work. This explains why binary search grows much more slowly than linear search.
