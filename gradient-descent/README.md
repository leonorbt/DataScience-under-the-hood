# Gradient Descent
Iterative first-order optimisation algorithm used to find a local minimum/maximum (minimizes a cost/loss function). If the function is strictly convex/concave, the minimum/maximum found will be global. It requires the fuction to be differentiable (have a derivative for each point in the domain).

## How does it work?
Pandas are cool

## What happens when the function is not convex/concave?
A function is strightly convex if any straight line segment between two points lies above the graph. If it touches the graph in any point other than the two points, it is considered to be convex. If a function (f) is convex, its negative (-f) is concave.

Alternatively, we can use meth ... A univariate function is convex if its second derivative is always bigger than 0. If the function has multiple variables, it's math on steroids (Hessian matrix).

If a function is strightly convex it can't have more than 1 minimum. However, it can have 0 minimums, when it continuosly decreases, as the exponential function. The same applies for strighly concave functions, where the logarithmic function doesn't have a maximum.

When the function is not convex nor concave, we risk getting stranded in a saddle point when using the gradient descent, that is, we find a local minimum (or maximum) that we can't exit.


## Sources
- https://towardsdatascience.com/gradient-descent-algorithm-a-deep-dive-cf04e8115f21 
- https://realpython.com/gradient-descent-algorithm-python/ 
