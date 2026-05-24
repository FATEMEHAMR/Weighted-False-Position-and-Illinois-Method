# Weighted False Position and Illinois Method

This project implements and compares two improved numerical root-finding methods in Python:

- **Modified False Position Method (Illinois Method)**
- **Improved / Weighted False Position Method**

The goal is to approximate the roots of nonlinear equations without using derivatives. These methods are based on the classical False Position method but improve its convergence behavior.

## Overview

Root-finding is an important topic in numerical analysis. Many nonlinear equations in engineering, physics, and applied mathematics do not have exact analytical solutions, so numerical methods are used to approximate their roots.

The classical False Position method works on an interval `[a, b]` where:

f(a) * f(b) < 0

This means the function changes sign in the interval, so a root exists between a and b.

Implemented Methods
Illinois Method

The Illinois method improves the classical False Position method by reducing the weight of an endpoint that remains unchanged for several iterations.
When one endpoint is retained, its function value is divided by 2, which helps the next approximation move faster toward the root.

Weighted False Position Method

The Weighted method calculates the next approximation using a dynamic weight:

w = |f(b)| / (|f(a)| + |f(b)|)
c = a * w + b * (1 - w)

This makes the method more adaptive and stable for different nonlinear functions.

Features
Finds roots of nonlinear equations
Implements two improved False Position methods
Accepts a custom function from the user
Accepts custom interval, tolerance, and maximum iterations
Prints a detailed iteration table
Shows values of a, b, c, f(a), f(b), f(c), and |b-a|
Checks the sign-change condition before starting
Reports the final root for both methods
Project Structure
.
├── main.py
├── report.pdf
└── README.md
Requirements

This project only uses Python’s standard library.

Python 3.x

No external packages are required.

How to Run
python main.py

After running the program, enter the required inputs:

f(x) = x**3 - x - 2
Enter a: 1
Enter b: 2
Enter tolerance: 1e-6
Enter max iterations: 100

You can also enter functions such as:

math.cos(x) - x
math.exp(-x) - x
math.sin(x)
x**2 - 4
Example Output
Root (Modified Method): 1.521380
Root (Improved Method): 1.521380

The program also prints the iteration table for each method.

Test Cases
Function	Interval	Expected Root
x^3 - x - 2	[1, 2]	1.52138
cos(x) - x	[0, 1]	0.739085
e^(-x) - x	[0, 1]	0.567143
x^2 - 4	[0, 3]	2
sin(x)	[3, 4]	3.14159
Comparison
Feature	Illinois Method	Weighted Method
Derivative required	No	No
Initial interval required	Yes	Yes
Convergence	Fast	Stable and smooth
Main idea	Halves retained endpoint value	Uses dynamic weighting
Complexity	Moderate	Simple
Limitations
The function must change sign in the selected interval.
The function should be continuous on [a, b].
The program uses eval() for user input, so it should only be used with trusted input.
Conclusion

This project shows how improved False Position methods can solve nonlinear equations efficiently without requiring derivatives. The Illinois method improves convergence speed by adjusting endpoint weights, while the Weighted method provides a smoother and more adaptive approximation process.
