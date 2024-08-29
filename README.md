# simplex


The Simplex method is an algorithm for solving linear programming problems. It is used to maximize or minimize a linear objective function subject to linear equality and inequality constraints.


Standard Form of Linear Programming Problem: A linear programming problem can be formulated in standard form as follows:
Maximize:
Z = c_1 * x_1 + c_2 * x_2 + ... + c_n * x_n
Subject to:
a_11 * x_1 + a_12 * x_2 + ... + a_1n * x_n <= b_1
a_21 * x_1 + a_22 * x_2 + ... + a_2n * x_n <= b_2
...
a_m1 * x_1 + a_m2 * x_2 + ... + a_mn * x_n <= b_m
x_1, x_2, ..., x_n >= 0
Where:
Z is the objective function to be maximized.
c_i are the coefficients of the objective function.
x_i are the decision variables.
a_ij are the coefficients of the constraints.
b_i are the right-hand side values of the constraints.
m is the number of constraints.
n is the number of variables.


Convert the linear programming problem into standard form.
Introduce slack variables to convert inequalities into equalities:
For each constraint of the form a_i1 * x_1 + ... + a_in * x_n <= b_i, introduce a slack variable s_i such that:
a_i1 * x_1 + ... + a_in * x_n + s_i = b_i
Ensure all variables (including slack variables) are non-negative.

Construct the initial tableau consisting of the coefficients of the objective function and the constraints.
The tableau is organized as follows:
The last row represents the objective function coefficients (negated).
Each constraint forms a row in the tableau.
Iterate to Find the Optimal Solution:

Check for Optimality:
Identify the pivot column (entering variable) by finding the most negative coefficient in the last row (objective function).
If all coefficients are non-negative, the current solution is optimal.

Determine the Leaving Variable:
Calculate the ratios of the right-hand side to the coefficients in the pivot column for each constraint:
ratio_i = tableau[i, -1] / tableau[i, entering]
Ignore negative or zero ratios.
The leaving variable is the basic variable associated with the smallest positive ratio.

Pivot Operation:
Normalize the pivot row by dividing it by the pivot element (intersection of the pivot row and pivot column).
Update the other rows to eliminate the pivot column entry by performing row operations.

Extract the Solution:
Once optimality is reached, read the solution from the tableau:
If a variable is basic (has a coefficient of 1 in its column), its value is taken from the rightmost column.
Non-basic variables have a value of zero.

Objective Value:
The optimal value of the objective function is found in the rightmost column of the last row.

Time Complexity:
The time complexity of the Simplex method is typically O(m * n^2), where m is the number of constraints and n is the number of variables, but the worst-case can be exponential in some cases.


The Simplex method is widely used due to its efficiency and effectiveness in solving linear programming problems.
It operates on the vertices of the feasible region defined by the constraints and finds the optimal vertex.
