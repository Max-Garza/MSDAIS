A conditional constraint where, if one or more things are true, one or more other - specified - things are true.

Assume x1-5
If x3 = 1, then x5 = 1
* x3 <= x5
If x2 = 1 and x3 = 1, then x4 = 1
* x2 + x3 - 1 <= x4
If x4 = 1 and x5 = 1, then x1 = 0
* x1 <= 2 - x4 - x5

Specific variables are affected by the truth statement.

- Background
	- [[Conditional Constraint]]