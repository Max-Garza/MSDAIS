After an integer programming model has been relaxed and solved, we must test different rounded values of the solution set to find the ideal values.

x1 = 3.5, x2 = 1.33

Branch 1.1 (int)                     Branch 1.2
x1 <= 3, x2 = int, OF = 120   x1 >= 4, OF = 127
                         Branch 2.1                      Branch 2.2 (int)
                         x2 <= 1, OF infeasible     x2 >= 2, OF = 123

- Background
	- [[Integer Programming]]
	- [[Solution]]