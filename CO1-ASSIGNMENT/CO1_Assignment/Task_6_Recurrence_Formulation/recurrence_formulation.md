# Task 6 – Recurrence Formulation

Let T(n) be the time for recursive binary search over an interval containing n elements.

For n > 1:
- The algorithm performs constant work: calculate the midpoint, compare the target and choose a branch.
- Exactly one recursive call is made on an interval of at most floor(n/2) elements.
- The base case is an empty interval (not found) or a constant-sized interval / matching midpoint.

A simplified recurrence is:
T(n) = T(n/2) + c, for n > 1
T(1) = d
where c and d are constants. For exact integer intervals, floor/ceiling terms may be used; they do not change the asymptotic result.
