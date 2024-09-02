---
title: Optimization in Math of Econ
date: 2024-09-02 15:32:08
tags:
categories:
- Math
- Optimization
---

# Basic Concepts
If a set is bounded and closed, then it's **compact**
- bounded: the boundary of the set is finite
- closed: the boundary of the set is reachable

## Extreme value theorem
- If the constrain set is compact and function $f$ is continuous, function has optimum.
- Note that this condition is **sufficient**.

# Interior optimum
## First order condition

If a function $f$ has an interior local maximizer or minimizer $x$ and if $f$ is differentiable at $x$, $f'(x)=0$

## Solving Procedure
1. Find all stationary points of $f$ in the interval by first order condition
2. Find values of $f$ at the endpoints (It's hard for multivariate function)
3. Compare and pick the point with largest $f(x)$

## Second order condition
### Single variable
- Sufficient and necessary condition for local optimum
- If $f''(x^*) < 0$ and $f'(x^*)=0$ for some inerior point $x^*$, then it's local maximizer.
- Similar for local minimizer.

### Multivariate

{% asset_img sce.png This is an example image %}

- For multivariate function, consider example $z=3xy-x^2-y^2$, (0,0) is the only stationary point, satisfing F.O.C and has $f''_{xx}\leq 0$ and $f''_{yy}\leq 0$, but (0,0) is not local optimizer. 
- Therefore, only if the hessian matrix is **negative definite** or **positive definite**, then it's local **maximizer** or local **minimizer**. And also, if it's minimizer or maximizer, then the hessian is **positive semedefinite** and **negative semidefinite**.
- The point (0,0) is a **saddle point**, it's stationary but not local optimizer.

# Optimization with Equality Constraint

$$
\max_{x, y} f(x, y) \\
s.t. \ g(x, y) = c
$$

{% asset_img lag1.png This is an example image %}

Therefore: 
$$
-\frac{f'_1(x^*, y^*)}{f'_2(x^*, y^*)}=-\frac{g'_1(x^*, y^*)}{g'_2(x^*, y^*)}
$$

Define $\lambda=\frac{f'_1(x^*, y^*)}{g'_1(x^*, y^*)}$, we get condition:
$$
f'_1(x^*, y^*) - \lambda g'_1(x^*, y^*) = 0 \\ 
f'_2(x^*, y^*) - \lambda g'_2(x^*, y^*) = 0 \\ 
c-g(x^*, y^*) = 0
$$

## Procedure
1. Find all the values of $(x, y, \lambda)$ that satisfies first order conditions and the constraint
2. Find points that satisfy $g_1'(x,y)=0$, $g_2'(x,y)=0$ and $g(x,y)=c$
3. Find points that is a boundary point and satisfy the constraint
4. Compair all the points

## Interpration of Lagrange multipliers
Write $x, y, \lambda$ as functions of $c$, we have $f'(c)=\partial f(x(c), y(c)) / \partial c = \lambda ^*(c)=\lambda ^*$

The value of **langrange multiplier** is equal to rate of change in the maximal value of the objective function with respect to $c$. (If the constraint loose a little bit, how much will the function increase?)

## Envelop theorem

### An example
Firm with profit $pf(x) - wx$ where $p$ is price of output, $f$ is production function, $x$ is input and $w$ is input price. Then, how does firm's maximum profit depend on $p$?

Write $\pi(w,p)=pf(x^*(w, p))-wx^*(w, p)$, taking derivative respect to $p$, we get 
$$
\frac{\partial \pi}{\partial p} = f(x^*(w, p)) + x^{*}_{p}{}'(w, p)[pf'(x^*(w,p))-w]
$$
, where $pf'(x^*(w,p))-w=0$ by F.O.C.

Therefore the result is $f(x^*(w, p))$

### Unconstrained version
Function has total $n+k$ variables, including $n$ decision variables $x$ and $k$ given parameters $r$. We define $x^*(r)$ as maximizer of $f$ given parameters $r$, then 
$$
f^*_h{}'(r) = f_{n+h}'(x^*(r), r)
$$
The impact of $h^{th}$ parameter on maximium value of function $f$, is the detivative of $f$ to the $h^{th}$ varaible at the optimal point.

### Constrained version
$n$ decisions, $m$ constraints, $k$ parameters. Indexed by $i$, $j$ and $h$ respectively. Define
$$
L(x, \lambda, r) = f(x, r) - \sum^m_{j=1}\lambda _jg_j(x, r)
$$
Then
$$
f_h^*{}'(r)=L'_{n+m+h}(x^*(r), \lambda (r), r)
$$

# Optimization with inequality constraints (KKT)

An example:

For a maximization problem

{% asset_img lag2.png This is an example image %}

- In left figure, it's equivalent to equality constraint optimization, given Lagrangean function $L(x)$, we have for all $i$ (index of x) that 
$$
L_i'(x^*) = 0
$$

- In right figure, it's equivalent to there's no condition at all, we have
$$
f_i'(x^*) = 0
$$

We can claim that in the first case, we have $\lambda \geq 0$, because a small change of $c$ should affect the value of $f$ (loose of constraint should increase the objective to be maximized). But, if $\lambda <0$, it means a decrease of $c$ raises the function, which is equivalent to **moving x inside the constraint raises the value of function**.

In the second case, given the interpration of $\lambda$ setting it to 0 seems reasonable. Actually, any $\lambda$ won't affect the result.

We can find that in the second case $L'_i(x^*) = 0$ because we set $\lambda$ to 0. Therefore, either in case 1, we have $g(x^*)=c$ or in case 2 we have $\lambda = 0$. 

The KT conditions are 
$$
L'_i(x)=0  \ \forall i  \\
\lambda_j \geq 0 \ \forall j  \\
g_j(x)\leq c_j \ \forall j \\
\lambda_j[g_j(x) - c_j] = 0 \ \forall j
$$