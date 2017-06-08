## Cost  Function

We can measure the accuracy of our hypothesis function by using a **cost function**. This takes an average difference \(actually a fancier version of an average\) of all the results of the hypothesis with inputs from x's and the actual output y's.

J\(θ0,θ1\)=12m∑i=1m\(y^i−yi\)2=12m∑i=1m\(hθ\(xi\)−yi\)2

To break it apart, it is12x¯wherex¯is the mean of the squares ofhθ\(xi\)−yi, or the difference between the predicted value and the actual value.

This function is otherwise called the "Squared error function", or "Mean squared error". The mean is halved\(12\)as a convenience for the computation of the gradient descent, as the derivative term of the square function will cancel out the12term. The following image summarizes what the cost function does:

![](/assets/Cost Function.png)

# Cost Function - Intuition I

If we try to think of it in visual terms, our training data set is scattered on the x-y plane. We are trying to make a straight line \(defined byhθ\(x\)\) which passes through these scattered data points.

Our objective is to get the best possible line. The best possible line will be such so that the average squared vertical distances of the scattered points from the line will be the least. Ideally, the line should pass through all the points of our training data set. In such a case, the value ofJ\(θ0,θ1\)will be 0. The following example shows the ideal situation where we have a cost function of 0.

![](/assets/Cost Function I-1.png)

Whenθ1=1, we get a slope of 1 which goes through every single data point in our model. Conversely, whenθ1=0.5, we see the vertical distance from our fit to the data points increase.

![](/assets/Cost Function I-2.png)

This increases our cost function to 0.58. Plotting several other points yields to the following graph:

![](/assets/Cost Funiction I-3.png)

Thus as a goal, we should try to minimize the cost function. In this case,θ1=1is our global minimum.

# Cost Function - Intuition II

A contour plot is a graph that contains many contour lines. A contour line of a two variable function has a constant value at all points of the same line. An example of such a graph is the one to the right below.

![](/assets/Cost Function II-1.png)

Taking any color and going along the 'circle', one would expect to get the same value of the cost function. For example, the three green points found on the green line above have the same value forJ\(θ0,θ1\)and as a result, they are found along the same line. The circled x displays the value of the cost function for the graph on the left whenθ0= 800 andθ1= -0.15. Taking another h\(x\) and plotting its contour plot, one gets the following graphs:

![](/assets/Cost Function II-2.png)

Whenθ0= 360 andθ1= 0, the value ofJ\(θ0,θ1\)in the contour plot gets closer to the center thus reducing the cost function error. Now giving our hypothesis function a slightly positive slope results in a better fit of the data.

![](/assets/Cost Function II-3.png)

The graph above minimizes the cost function as much as possible and consequently, the result ofθ1andθ0tend to be around 0.12 and 250 respectively. Plotting those values on our graph to the right seems to put our point in the center of the inner most 'circle'.

