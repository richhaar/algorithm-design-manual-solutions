# 1.10 Exercises
## Finding Counter Examples
### 1-1
> Show that `a + b` can be less than `min(a,b)`

If we take negative values, such as `a =-1, b=-2`,
then `min(a,b) = -2` and `a+b = -3`.
### 1-2
>Show that `a x b` can be less than `min(a,b)`

If one value is `0` and the other negative such as `a=-1, b=0` then `min(a,b) = -1` but the product is `0`.

### 1-3
> Design/draw a road network with two points `a` and `b` such that the fastest route between `a` and `b` is not the shorted route

![img](./fig1-3.png)

### 1-4
> Design/draw a road network with two points `a` and `b` such that the shortest route between $a$ and `b` is not the route with the fewest turns

![img](./fig1-4.png)

### 1-5

>The knapsack problem is as follows: given a set `S` of subsets `S_1,...,S_M` and a target number `T`, find a subset of `S` that adds up exactly to `T`. For example, there exists a subset within `S = {1,2,5,9,10}` that adds up to `T = 22` but not `T = 23`. Find counterexamples to each of the following algorithms for the knapsack problem. That is, give an `S` and `T` where the algorithm does not find a solution that leaves the kanpsack completely full, even though a full-knapsack solution exists.

> (a) Put the elements of S in the knapsack in left to right order if they fit, that is the first-fit algoritm

S = {4,5,10} T = 10

> (b) Put the elements of S in the knapsack from smallest to largest, that is the best fit algorithm

S = {1,2,3,7} T = 9

> (c) Put the elements of S in the knapsack from largest to smallest.

S = {7,8,14} T = 15

### 1-6

>The set cover problem is as follows: given a set S of subsets S_1,...,S_m of the universal set U = {1,...,n}, find the smallest subset of subsets T ⊆ S such that the union of sets t = U. For example, consider the subsets S_1 = {1,3,5}, S_2 = {2,4}, S_3 = {1,4}, and S_4 = {2,5}. The set cover of {1,...,5} would then be S_1 and S_2. Find a counterexample for the following algorithm: Select the largest subset for the cover, and then delete all its elements from the universal set. Repeat by adding the subset containing the largest number of unocvered elements until all are covered.


Consider U = {1,2,3,4, 5} subsets {1,2,3} {1,2,5} {3,4}

Since the largest set here has a choice of two, it can choose {1,2,3} and the rest sets become:

{5} and {4}, picks {5} and then {4} to get {1,2,3,4,5} covered.

However the optimal is {1,2,5} and {3,4}

### 1-7

>The maximum clique problem in a graph G = (V, E) asks for the largest subset C of vertices V such that there is an edge E between every pair of vertices in C. Find a counterexample for the following algorithm: Sort the vertices of G from highest to lowest degree. Considering the vertices in order of degree, for each vertex add it to the clique if it is a neighbour of all vertices currently in the clique, repeat until all vertices have been considered.


![img](./fig1-7.png)

The algorithm wil find a clique of two (nodes in red) and not the optimal clique of three (in green).


## Proofs of correctness

### 1-8

> Prove the correctness of the following recursive algorithm to multiply two natural numbers, for all integer constants c >= 2.

```
Multiply(y,z)
	if z = 0 then return(0) else
	return(Multiply(cy, ⌊z/c⌋) + y · (z mod c))
```

>For when z = 0

Multiply(y,0) = 0

> For when z = 1

Multiply(y,1) = Multiply(cy, 0) + y(1 mod c) = 0 + y = y;

> For when z = 2

Multiply(y,2) = Multiply(cy, ⌊z/c⌋) + y(z mod c)

which for c =2 is:

Multiply(y,2) = Multiply(2y, 1) + y(2 mod 2) = 2y + 0 = 2y

for when c >2 :

Multiply(y,2) = Multiply(cy, 0) + y(c mod 2) = 0 + cy = cy

> Assume z == c

Multiply(y,c) = Multiply(yc, 1) + y (c mod c) = yc;

> Assume z < c

Multiply(y, z) = Multiply(yc, 0) + y * z = yz;

> Assume z > c

Multiply(y, c+1) = Mutiply(cy, 1) + y (c+1 mod c) = cy + y = y(c+1)

> c is 2 is proven, prove c>2

Multiply(y, c+2) = Multiply(cy, 2) + y(2) = cy + 2y = c(y+2)

> Prove 2c-1 

Multiply(y, 2c-1) = Multiply(cy, 1), y(c-1) = cy + y(c-1) = y(2c-1)

> Prove nc

Mutiply(y, nc) = Multiply(cy, n), y(0) = Multiply(cy, n)

Multiply(y nc+x) = Multiply(cy, n) + y(nc+x mod c) = Multiply(cy, n) + yx

which will then eventually reduce to nc < 2c and qed


or alternatively prove Multiply(y,z) == Multiply(z,y) and with above it proves it.

Proof needs some work to make it concise

### 1-9

Prove the correctness of the following algorithm for evaluating a polynomial:

a_nx^n + a_(n-1)x^(n-1) + ... + a_1x + a_0.

```
	Horner(a, x)
		p = a_n
		for i from n-1 to 0
			p = p*x + a_i
		return p;
```

> For when n = 0

p = a_0

> For when n = 1

p_1 = a_1 * x + a_0

> for when n = 2

p_2 = (a_2 * x + a_1) * x + a_0

> for when n -1:

p_(n-1) = ((a_(n-1) *  x + a_(n-2)) * x + a_(n-3)) * x .... + a_0


Proof needs work






