# Gradient Descent

So we have our hypothesis function and we have a way of measuring how well it fits into the data. Now we need to estimate the parameters in the hypothesis function. That's where gradient descent comes in.

Imagine that we graph our hypothesis function based on its fieldsθ0andθ1\(actually we are graphing the cost function as a function of the parameter estimates\). We are not graphing x and y itself, but the parameter range of our hypothesis function and the cost resulting from selecting a particular set of parameters.

We putθ0on the x axis andθ1on the y axis, with the cost function on the vertical z axis. The points on our graph will be the result of the cost function using our hypothesis with those specific theta parameters. The graph below depicts such a setup.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/bn9SyaDIEeav5QpTGIv-Pg_0d06dca3d225f3de8b5a4a7e92254153_Screenshot-2016-11-01-23.48.26.png?expiry=1496793600000&hmac=DavdOmNq35KaxHDgkhLDP8kEy2f26wvKmMg1XQ52me4)

We will know that we have succeeded when our cost function is at the very bottom of the pits in our graph, i.e. when its value is the minimum. The red arrows show the minimum points in the graph.

The way we do this is by taking the derivative \(the tangential line to a function\) of our cost function. The slope of the tangent is the derivative at that point and it will give us a direction to move towards. We make steps down the cost function in the direction with the steepest descent. The size of each step is determined by the parameter α, which is called the learning rate.

For example, the distance between each 'star' in the graph above represents a step determined by our parameter α. A smaller α would result in a smaller step and a larger α results in a larger step. The direction in which the step is taken is determined by the partial derivative ofJ\(θ0,θ1\). Depending on where one starts on the graph, one could end up at different points. The image above shows us two different starting points that end up in two different places.

The gradient descent algorithm is:

repeat until convergence:

θj:=θj−α∂∂θjJ\(θ0,θ1\)

where

j=0,1 represents the feature index number.

At each iteration j, one should simultaneously update the parametersθ1,θ2,...,θn. Updating a specific parameter prior to calculating another one on thej\(th\)iteration would yield to a wrong implementation.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/yr-D1aDMEeai9RKvXdDYag_627e5ab52d5ff941c0fcc741c2b162a0_Screenshot-2016-11-02-00.19.56.png?expiry=1496793600000&hmac=wJ_VPTTPmgE2QGp2q_geYE-Adk2ybAySG11CYs1njUE)

# Gradient Descent Intuition

In this video we explored the scenario where we used one parameterθ1and plotted its cost function to implement a gradient descent. Our formula for a single parameter was :

Repeat until convergence:

| θ1:=θ1−αddθ1J\(θ1\) |
| :--- |


Regardless of the slope's sign forddθ1J\(θ1\),θ1eventually converges to its minimum value. The following graph shows that when the slope is negative, the value ofθ1increases and when it is positive, the value ofθ1decreases.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/SMSIxKGUEeav5QpTGIv-Pg_ad3404010579ac16068105cfdc8e950a_Screenshot-2016-11-03-00.05.06.png?expiry=1496793600000&hmac=klUfem3vYb5I2mYm8gDwiiWl9nQbWk9j1uxD2HLprT0)

On a side note, we should adjust our parameterαto ensure that the gradient descent algorithm converges in a reasonable time. Failure to converge or too much time to obtain the minimum value imply that our step size is wrong.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/UJpiD6GWEeai9RKvXdDYag_3c3ad6625a2a4ec8456f421a2f4daf2e_Screenshot-2016-11-03-00.05.27.png?expiry=1496793600000&hmac=1tM4m2p3ig7lroH2sXP8XvC7y7T_qz1uyaqfdxDBnQ0)

### How does gradient descent converge with a fixed step sizeα?

The intuition behind the convergence is thatddθ1J\(θ1\)approaches 0 as we approach the bottom of our convex function. At the minimum, the derivative will always be 0 and thus we get:

| θ1:=θ1−α∗0 |
| :--- |




![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/RDcJ-KGXEeaVChLw2Vaaug_cb782d34d272321e88f202940c36afe9_Screenshot-2016-11-03-00.06.00.png?expiry=1496793600000&hmac=qY0E7qDGYKLjpVmJbRCPMGMG8lF0cFzcx20ENpQGKQg)

