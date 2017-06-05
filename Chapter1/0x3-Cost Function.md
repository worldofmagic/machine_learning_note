## Cost  Function

We can measure the accuracy of our hypothesis function by using a **cost function**. This takes an average difference \(actually a fancier version of an average\) of all the results of the hypothesis with inputs from x's and the actual output y's.

J\(θ0,θ1\)=12m∑i=1m\(y^i−yi\)2=12m∑i=1m\(hθ\(xi\)−yi\)2

To break it apart, it is12x¯wherex¯is the mean of the squares ofhθ\(xi\)−yi, or the difference between the predicted value and the actual value.

This function is otherwise called the "Squared error function", or "Mean squared error". The mean is halved\(12\)as a convenience for the computation of the gradient descent, as the derivative term of the square function will cancel out the12term. The following image summarizes what the cost function does:

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/R2YF5Lj3EeajLxLfjQiSjg_110c901f58043f995a35b31431935290_Screen-Shot-2016-12-02-at-5.23.31-PM.png?expiry=1496793600000&hmac=aPSRwmZYbftou-_I-eaW7sGUxLnw-3_TuugmZhVxwvM)



# Cost Function - Intuition I

If we try to think of it in visual terms, our training data set is scattered on the x-y plane. We are trying to make a straight line \(defined byhθ\(x\)\) which passes through these scattered data points.

Our objective is to get the best possible line. The best possible line will be such so that the average squared vertical distances of the scattered points from the line will be the least. Ideally, the line should pass through all the points of our training data set. In such a case, the value ofJ\(θ0,θ1\)will be 0. The following example shows the ideal situation where we have a cost function of 0.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/_B8TJZtREea33w76dwnDIg_3e3d4433e32478f8df446d0b6da26c27_Screenshot-2016-10-26-00.57.56.png?expiry=1496793600000&hmac=dIczbVnmXI2GPUSzI7XaLtp67vFfBCSCN-3yqH-rbz8)

Whenθ1=1, we get a slope of 1 which goes through every single data point in our model. Conversely, whenθ1=0.5, we see the vertical distance from our fit to the data points increase.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/8guexptSEeanbxIMvDC87g_3d86874dfd37b8e3c53c9f6cfa94676c_Screenshot-2016-10-26-01.03.07.png?expiry=1496793600000&hmac=d1tHPExg-hCX7RHDjrYVXfPYdVmyMW8KIKIEljFIw-Y)

This increases our cost function to 0.58. Plotting several other points yields to the following graph:

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/fph0S5tTEeajtg5TyD0vYA_9b28bdfeb34b2d4914d0b64903735cf1_Screenshot-2016-10-26-01.09.05.png?expiry=1496793600000&hmac=2aho71stW4eEZXPweTpGhqJBA-b-LIvVL3Fh9t3q0WA)

Thus as a goal, we should try to minimize the cost function. In this case,θ1=1is our global minimum.



