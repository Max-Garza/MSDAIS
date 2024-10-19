1. Convert all functional constraints to decision variables
2. Convert the constraint right hand sides to objective coefficients
3. Convert decision variables to functional constraints
4. Convert functional constraint coefficients to a transposed set of functional constraint coefficients
5. Convert non-functional constraint comparison symbols to functional constraint comparison symbols
	1. If MAX -> MIN, signs do not flip
	2. If MIN -> MAX, signs flip
6. Convert objective function coefficients to functional constraint right hand sides
7. Convert functional constraint comparison symbols to non-functional constraint comparison symbols
	1. If MAX -> MIN, signs flip
	2. If MIN -> MAX, signs do not flip

![[Pasted image 20241005183805.png]]

- Background
	- [[Duality]]
	- [[Functional Constraint]]
	- [[Decision Variable]]
	- [[Objective Coefficient]]
	- [[Coefficient]]
	- [[Non-Functional Constraint]]