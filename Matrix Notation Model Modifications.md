To force a model to fit matrix notation, some modifications may be needed.

* Constraint Comparison Symbols
	* If <=, no change
	* If >=, multiply both sides by -1 and take <= sign
	* If =, break into two constraints: ax <= b, -ax <= -b
* Variable modifications
	* Negative variables
		* Convert x to x', where x <= 0 and x' >= 0
		* Replace all x in the model with -x'
	* Unrestricted variables
		* convert x to x'-x'', where x UNR, x' >= 0, x'' >= 0

- Background
	- [[Matrix Notation]]