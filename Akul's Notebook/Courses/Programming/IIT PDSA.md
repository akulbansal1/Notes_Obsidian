
## Programming, Data Structures, and Algorithms using Python
# <u>Week 1</u>

# <u>Week 2</u>

- Resources of interest:
	1. Time — how long the code takes
	2. Space — memory requirement
- Time efficiency:
	- measured as a function of input size $n$
	- $t(n)$
	- Orders of magnitude:
		- when comparing $t(n)$, focus on orders of magnitude and not the constants
	- Typical growth functions:
		- logarithmic: $log_{2}(n)$: binary search (dividing the ordered dataset in two at every step)
		- polynomial: $n^2, n^3, \ldots$: nested loops
		- exponential: $2^n$: number of subsets of $n$
	- Typical basic operations: 
		- compare two values: `y == x`
		- assign a value to a variable: `x = 3`
- Upper bounds: denoted by $O(g(x))$
	- $f(x)$ is said to be $O(g(x))$ if we can find constants $c$ and $x_0$ such that $c \cdot g(x)$ is an upper bound for $f(x)$ for $x$ beyond $x_0$ $$ f(x)\ \leq\ c \cdot g(x) \quad \forall x \geq x_0$$
	- example: $100n + 5$ is $O(n^2)$
		- $100n + 5 \leq 100n + n \quad \forall n \geq 5$  and $100n + n = 101n$
		- $101n \leq 101n^2$
		- $c = 101$ and $n_0 = 5$
		- choice of $n_0$ and $c$ is not unique. $c = 105$ and $n_0 = 1$ is also a solution.
	- **Useful properties**
		- if $f_1(n)$ is $O(g_1(n))$ and $f_2(n)$ is $O(g_2(n))$, then $f_1(n) + f_2(n)$ is $O(max(g_1(n),g_2(n)))$
		- least efficient phase is the upper bound for the whole algorithm.
- Lower bounds : denoted by $\Omega(g(x))$
	- $f(x)$ is said to be $\Omega(g(x))$ if we can find constants $c$ and $x_0$ such that $c \cdot g(x)$ is an lower bound for $f(x)$ for $x$ beyond $x_0$ $$ f(x)\ \geq\ c \cdot g(x) \quad \forall x \geq x_0$$
- Tight bounds: denoted by $\Theta(g(x))$
	- $f(x)$ is said to be $\Theta(g(x))$ if it is both $O(g(x))$ and $\Omega(g(x))$
	- example: $\frac{n(n-1)}{2}$ is $\Theta(n^2)$

- Iterative programs
	- 
- Recursive programs