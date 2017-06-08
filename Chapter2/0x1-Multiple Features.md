# Multiple Features

**Note:**\[7:25 -θTis a 1 by \(n+1\) matrix and not an \(n+1\) by 1 matrix\]

Linear regression with multiple variables is also known as "multivariate linear regression".

We now introduce notation for equations where we can have any number of input variables.

$$ x ^{\(i\)}\_j$$$$ x_j^{(i)}$$** = value of feature **$$j$$** in the **$$i^{th}$$** traning example**

$$x^{(i)}$$** = the column vector of all the feature inputs of the **$$i^{th}$$** training example**

**m = the number of training examples**

**n = **$$ \mid x^{(i)} \mid$$**;\(the number of features\) **

The multivariable form of the hypothesis function accommodating these multiple features is as follows:

$$h_\theta(x)$$ = $$\theta_0$$+$$ \theta_{1}x_{1}$$+ $$ \theta_{2}x_{2}$$+ $$\theta_{3}x_{3}$$+...+ $$ \theta_{n}x_{n}$$

In order to develop intuition about this function, we can think about $$\theta_{0}$$ as the basic price of a house, $$\theta_{1}$$ as the price per square meter, $$\theta_{2}$$ as the price per floor, etc. $$x_{1}$$ will be the number of square meters in the house, $$x_{2}$$ the number of floors, etc.

Using the definition of matrix multiplication, our multivariable hypothesis function can be concisely represented as:

$$h_{\theta}(x)$$ = \[ \[ $$\theta_{0}$$+$$\theta_{1}$$+...+$$\theta_{n}$$ \] \] \* \[\[$$x_{0}$$\],\[$$x_{1}$$\],...\[$$x_{n}$$\]\]

This is a vectorization of our hypothesis function for one training example; see the lessons on vectorization to learn more.

Remark: Note that for convenience reasons in this course we assumex\(i\)0=1 for \(i∈1,…,m\). This allows us to do matrix operations with theta and x. Hence making the two vectors 'θ' andx\(i\)match each other element-wise \(that is, have the same number of elements: n+1\).\]

The following example shows us the reason behind settingx\(i\)0=1:

X=⎡⎣x\(1\)0x\(1\)1x\(2\)0x\(2\)1x\(3\)0x\(3\)1⎤⎦,θ=\[θ0θ1\]

As a result, you can calculate the hypothesis as a vector with:

hθ\(X\)=θTX

