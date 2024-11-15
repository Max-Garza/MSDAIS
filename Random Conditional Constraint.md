A conditional constraint where, if one or more things are true, one or more other - unspecified - things are true.

Assume x1-5
If x2 = 1, then 2+ other variables = 1
* 2(x2) <= x1 + x3 + x4 + x5
If x3 = 1, then 2- other variables = 1
* x1 + x2 + x4 + x5 <= 2(x3)
If x4 = 1, then 1+ other variables = 1
* x4 <= x1 + x2 + x3 + x5

Any variable can be affected by the truth statement.

* Background
	* [[Conditional Constraint]]