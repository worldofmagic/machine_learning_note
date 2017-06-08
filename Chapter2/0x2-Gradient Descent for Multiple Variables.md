# Gradient Descent For Multiple Variables

The gradient descent equation itself is generally the same form; we just have to repeat it for our 'n' features:

![](/assets/GDMV 1.png)

In other words:

![](/assets/GDMV 2.png)

The following image compares gradient descent with one variable to gradient descent with multiple variables:

![](/assets/GDMV 3.png)

## Gradient Descent in Practice I - Feature Scaling

**Note:**\[6:20 - The average size of a house is 1000 but 100 is accidentally written instead\]

We can speed up gradient descent by having each of our input values in roughly the same range. This is because θ will descend quickly on small ranges and slowly on large ranges, and so will oscillate inefficiently down to the optimum when the variables are very uneven.

The way to prevent this is to modify the ranges of our input variables so that they are all roughly the same. Ideally:

$$ −1 \leqslant x_{(i)} \leqslant 1 $$

or

$$ −0.5 \leqslant x_{(i)} \leqslant 0.5$$

These aren't exact requirements; we are only trying to speed things up. The goal is to get all input variables into roughly one of these ranges, give or take a few.

Two techniques to help with this are **feature scaling **and **mean normalization**. Feature scaling involves dividing the input values by the range \(i.e. the maximum value minus the minimum value\) of the input variable, resulting in a new range of just 1. Mean normalization involves subtracting the average value for an input variable from the values for that input variable resulting in a new average value for the input variable of just zero. To implement both of these techniques, adjust your input values as shown in this formula:

$$ x_{i} :=(x_{i} - \mu_{i})/s_{i}$$

Whereμiis the **average **of all the values for feature \(i\) andsiis the range of values \(max - min\), orsiis the standard deviation.

Note that dividing by the range, or dividing by the standard deviation, give different results. The quizzes in this course use range - the programming exercises use standard deviation.

For example, ifxirepresents housing prices with a range of 100 to 2000 and a mean value of 1000, then,

$$ x_{i}$$ $$:=$$ $$(price-1000)/1900$$.



## Gradient Descent in Practice II - Learning Rate

**Note:**\[5:20 - the x -axis label in the right graph should beθrather than No. of iterations \]

**Debugging gradient descent.**Make a plot with_number of iterations_on the x-axis. Now plot the cost function, J\(θ\) over the number of iterations of gradient descent. If J\(θ\) ever increases, then you probably need to decrease α.

**Automatic convergence test.**Declare convergence if J\(θ\) decreases by less than E in one iteration, where E is some small value such as10−3. However in practice it's difficult to choose this threshold value.

![](/assets/GDMV PII.png)

It has been proven that if learning rate α is sufficiently small, then J\(θ\) will decrease on every iteration.

![](/assets/GDMV PII-2.png)

To summarize:

Ifαis too small: slow convergence.

Ifαis too large: ￼may not decrease on every iteration and thus may not converge.

