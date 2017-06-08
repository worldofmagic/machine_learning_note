# Gradient Descent

So we have our hypothesis function and we have a way of measuring how well it fits into the data. Now we need to estimate the parameters in the hypothesis function. That's where gradient descent comes in.

Imagine that we graph our hypothesis function based on its fieldsθ0andθ1\(actually we are graphing the cost function as a function of the parameter estimates\). We are not graphing x and y itself, but the parameter range of our hypothesis function and the cost resulting from selecting a particular set of parameters.

We putθ0on the x axis andθ1on the y axis, with the cost function on the vertical z axis. The points on our graph will be the result of the cost function using our hypothesis with those specific theta parameters. The graph below depicts such a setup.

![](/assets/Gardient descent 1.png)

We will know that we have succeeded when our cost function is at the very bottom of the pits in our graph, i.e. when its value is the minimum. The red arrows show the minimum points in the graph.

The way we do this is by taking the derivative \(the tangential line to a function\) of our cost function. The slope of the tangent is the derivative at that point and it will give us a direction to move towards. We make steps down the cost function in the direction with the steepest descent. The size of each step is determined by the parameter α, which is called the learning rate.

For example, the distance between each 'star' in the graph above represents a step determined by our parameter α. A smaller α would result in a smaller step and a larger α results in a larger step. The direction in which the step is taken is determined by the partial derivative ofJ\(θ0,θ1\). Depending on where one starts on the graph, one could end up at different points. The image above shows us two different starting points that end up in two different places.

The gradient descent algorithm is:

repeat until convergence:

θj:=θj−α∂∂θjJ\(θ0,θ1\)

where

j=0,1 represents the feature index number.

At each iteration j, one should simultaneously update the parametersθ1,θ2,...,θn. Updating a specific parameter prior to calculating another one on thej\(th\)iteration would yield to a wrong implementation.

![](/assets/Gardient descent 2.png)

# Gradient Descent Intuition

In this video we explored the scenario where we used one parameterθ1and plotted its cost function to implement a gradient descent. Our formula for a single parameter was :

Repeat until convergence:

| θ1:=θ1−αddθ1J\(θ1\) |
| :--- |


Regardless of the slope's sign forddθ1J\(θ1\),θ1eventually converges to its minimum value. The following graph shows that when the slope is negative, the value ofθ1increases and when it is positive, the value ofθ1decreases.

![](/assets/Gardient descent intuition 1.png)

On a side note, we should adjust our parameterαto ensure that the gradient descent algorithm converges in a reasonable time. Failure to converge or too much time to obtain the minimum value imply that our step size is wrong.

![](/assets/Gardient descent intuition 2.png)

### How does gradient descent converge with a fixed step sizeα?

The intuition behind the convergence is thatddθ1J\(θ1\)approaches 0 as we approach the bottom of our convex function. At the minimum, the derivative will always be 0 and thus we get:

| θ1:=θ1−α∗0 |
| :--- |


![](/assets/Gardient descent intuituin 3.png)

# Gradient Descent For Linear Regression

**Note:**\[At 6:15 "h\(x\) = -900 - 0.1x" should be "h\(x\) = 900 - 0.1x"\]

When specifically applied to the case of linear regression, a new form of the gradient descent equation can be derived. We can substitute our actual cost function and our actual hypothesis function and modify the equation to :

| repeat until convergence: {θ0:=θ1:=}θ0−α1m∑i=1m\(hθ\(xi\)−yi\)θ1−α1m∑i=1m\(\(hθ\(xi\)−yi\)xi\) |
| :--- |


where m is the size of the training set,θ0a constant that will be changing simultaneously withθ1andxi,yiare values of the given training set \(data\).

Note that we have separated out the two cases forθjinto separate equations forθ0andθ1; and that forθ1we are multiplyingxiat the end due to the derivative. The following is a derivation of∂∂θjJ\(θ\)for a single example :

![](/assets/Gradient.png)

The point of all this is that if we start with a guess for our hypothesis and then repeatedly apply these gradient descent equations, our hypothesis will become more and more accurate.

So, this is simply gradient descent on the original cost function J. This method looks at every example in the entire training set on every step, and is called**batch gradient descent**. Note that, while gradient descent can be susceptible to local minima in general, the optimization problem we have posed here for linear regression has only one global, and no other local, optima; thus gradient descent always converges \(assuming the learning rate α is not too large\) to the global minimum. Indeed, J is a convex quadratic function. Here is an example of gradient descent as it is run to minimize a quadratic function.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/xAQBlqaaEeawbAp5ByfpEg_24e9420f16fdd758ccb7097788f879e7_Screenshot-2016-11-09-08.36.49.png?expiry=1496793600000&hmac=O13JIlbcHrKhqh4TASCi4iDr0XJekqbu1EQdCyqXIFM)

The ellipses shown above are the contours of a quadratic function. Also shown is the trajectory taken by gradient descent, which was initialized at \(48,30\). The x’s in the figure \(joined by straight lines\) mark the successive values of θ that gradient descent went through as it converged to its minimum.

