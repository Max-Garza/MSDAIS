If there are multiple changes in an optimization problem, one cannot refer to the allowable increase, allowable decrease, objective coefficient, or constraint right hand side directly.

Instead, calculate the percent change between the allowable change and the value you want to change to. Then, take the sum of these percentages. If the sum is less than 100%, then the change is allowable.

Take two decision variables:
	A, objective coefficient = 300, Allowable Increase = 50, Allowable Decrease = 200
	B, objective coefficient = 200, Allowable Increase = 100, Allowable Decrease = 10

If we want to see if we can change both of our objective coefficients to 250, we would do the following:
$$\begin{align}
& a \|\ \frac{300-250}{200} \\
& b \|\ \frac{250-200}{100} \\
& 0.25 + 0.5 = 0.75 < 1
\end{align}$$
Because the sum of these is less than 1, we know our solution is still valid.

- Background
	- [[Solution]]
	- [[Optimization]]
	- [[Allowable Increase or Decrease (Variable Report)]]
	- [[Allowable Increase or Decrease (Constraint Report)]]
	- [[Objective Coefficient]]
	- [[Constraint Right Hand Side]]
	- [[Decision Variable]]