The most compact form of optimization problem representation.
$$MIN/MAX f^t x$$
$$ST Ax <= b  \ or \ Ax = b$$
$$x >= 0$$
Network
$$MIN/MAX c^t x$$
$$ST Ax = b$$
$$lb <= x <= ub$$

Where
* *f* = objective function coefficients (set)
* *x* = decision variables (set)
* *A* = constraint coefficients (matrix)
* *b* = constraint RHS (set)
* *lb* = variable lower bounds (set)
* *ub* = variable upper bounds (set)

- Background
	- [[Optimization]]
	- [[Network Optimization]]