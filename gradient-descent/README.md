# Gradient Descent
Iterative first-order optimisation algorithm used to find a local minimum/maximum (minimizes a cost/loss function). If the function is strictly convex/concave, the minimum/maximum found will be global. It requires the fuction to be differentiable (have a derivative for each point in the domain). It will take bigger steps when it's far from the minimum/maximum and smaller steps as it get closer.

## How does it work?
Let's explain it in minimization of a cost function to simplify, but the logic can also be applied to find a maximum.
1. Define a random point as the starting point.
2. Compute the gradient, that is, the first order derivative.
3. Move the point by the gradient * learning rate (it's a subtraction because we are going for the minimum)
4. Repeat steps 2 and 3 until the number of iterations or the tolerance is reached

### What is the learning rate?
It is the step at which your algorithm evolves. If the value is too high, we might miss the minimum. If the value is too low, we might reach the number of iterations before finding the minimum and will have a very slow algorithm.

### What is the tolerance?
It is the "acceptable error". If taking the new step will improve the algorithm by a very small amount, we are likely close to a minimum (could be a saddle point) and there is no need to continue running it, so we break.

## What happens when the function is not convex/concave?
A function is strightly convex if any straight line segment between two points lies above the graph. If it touches the graph in any point other than the two points, it is considered to be convex. If a function (f) is convex, its negative (-f) is concave.

Alternatively, we can use meth ... A univariate function is convex if its second derivative is always bigger than 0 (the second derivative informs whether the slope of the tangent line is increasing or decreasing). If the function has multiple variables, it's math on steroids (Hessian matrix).

If a function is strightly convex it can't have more than 1 minimum. However, it can have 0 minimums, when it continuosly decreases, as the exponential function. The same applies for strighly concave functions, where the logarithmic function doesn't have a maximum.

When the function is not convex nor concave, we risk getting stranded in a saddle point when using the gradient descent, that is, we find a local minimum (or maximum) that we can't exit.

## Gradient Descent applied to a Linear Regression
Let's put the Gradient Descent in practice by trying to find the parameters of a Linear Regression!

To get the parameters of the Linear Regression, we want to minimize the **Sum of Squared Residuals (SSR)**, which is the squared difference between the real value and the expected value (SSR = Σᵢ(𝑦ᵢ − 𝑓(𝐱ᵢ))²) summed for each observation.

#### Linear Regression
𝑓(𝑥) = 𝑏₀ + 𝑏₁𝑥, being 𝑏₀ the intercept

#### Cost Function
It should be SSR or MSE (Mean Squared Error, SSR/n), but the SSR / (2𝑛) is seen as mathematically more convenient as the first derivative will be multiplied by 2 and cancel out the denominator.

### In practice
1. Get the cost function: C = SSR = Σᵢ(𝑦ᵢ − 𝑓(𝐱ᵢ))² = Σᵢ(𝑦ᵢ − (𝑏₀ + 𝑏₁𝑥ᵢ))² = Σᵢ(𝑦ᵢ − 𝑏₀ - 𝑏₁𝑥ᵢ)² 
2. Compute the gradient vector, which is the derivative in order of each parameter
- Intercept: ∂𝐶/∂𝑏₀ = 2 * Σᵢ(-𝑦ᵢ + 𝑏₀ + 𝑏₁𝑥ᵢ) = 2 * Σᵢ(𝑏₀ + 𝑏₁𝑥ᵢ - 𝑦ᵢ)
- Parameter: ∂𝐶/∂𝑏₁ =  2 * Σᵢ(𝑏₀ + 𝑏₁𝑥ᵢ - 𝑦ᵢ)𝑥ᵢ
3. Pandas

## Sources
- https://towardsdatascience.com/gradient-descent-algorithm-a-deep-dive-cf04e8115f21 
- https://realpython.com/gradient-descent-algorithm-python/ 
- https://www.mathsisfun.com/calculus/derivative-plotter.html (this has great viz on derivatives)
