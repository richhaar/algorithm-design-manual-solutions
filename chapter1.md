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

The algorithm wil find a clique of two and not the optimal clique of three.






