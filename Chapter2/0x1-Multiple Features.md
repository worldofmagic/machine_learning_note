# Multiple Features

**Note:**\[7:25 -θTis a 1 by \(n+1\) matrix and not an \(n+1\) by 1 matrix\]

Linear regression with multiple variables is also known as "multivariate linear regression".

We now introduce notation for equations where we can have any number of input variables.

$$ x ^{\(i\)}\_j$$$$ x_j^{(i)}$$** = value of feature **$$j$$** in the **$$i^{th}$$** traning example**

$$x^{(i)}$$** = the column vector of all the feature inputs of the **$$i^{th}$$** training example**

**m = the number of training examples**

**n = **$$ \mid x^{(i)} \mid$$**;\(the number of features\) **

The multivariable form of the hypothesis function accommodating these multiple features is as follows:

$$h_{\theta}(x)$$ = $$[\theta_{0} \quad \theta_{1} \quad ... \theta_{n} \quad]$$$$[[x{0}] [x{1}][...][x{n}]]$$ = $$ \theta^{T}x$$

In order to develop intuition about this function, we can think about $$\theta_{0}$$ as the basic price of a house, $$\theta_{1}$$ as the price per square meter, $$\theta_{2}$$ as the price per floor, etc. $$x_{1}$$ will be the number of square meters in the house, $$x_{2}$$ the number of floors, etc.

Using the definition of matrix multiplication, our multivariable hypothesis function can be concisely represented as:

$$h_{\theta}(x)$$ = \[ \[ $$\theta_{0}$$+$$\theta_{1}$$+...+$$\theta_{n}$$ \] \] \* \[\[$$x_{0}$$\],\[$$x_{1}$$\],...\[$$x_{n}$$\]\]

This is a vectorization of our hypothesis function for one training example; see the lessons on vectorization to learn more.

Remark: Note that for convenience reasons in this course we assume $$x_{0}^{i}=1$$ for \($$i \in 1,...,m$$\). This allows us to do matrix operations with theta and x. Hence making the two vectors '$$\theta$$' and $$x^{(i)}$$ match each other element-wise \(that is, have the same number of elements: n+1\).\]

The following example shows us the reason behind setting $$x_{0}^{(i)}=1$$:

$$ X = [ [ x_{0}^{(1)} , x_{0}^{(2)},x_{0}^{(3)} ],[ x_{1}^{(1)} , x_{1}^{(2)},x_{1}^{(3)} ] ]$$, $$ \theta = [ [ \theta_{0} ], [\theta_{1}] ]$$

As a result, you can calculate the hypothesis as a vector with:

$$ h_{\theta}(X) = \theta^{T}X$$

