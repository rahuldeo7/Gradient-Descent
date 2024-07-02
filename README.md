Alternative Gradient Descent Algorithm
This document provides a theoretical and mathematical explanation of the alternative gradient descent algorithm implemented in the provided Python code. This algorithm is used to estimate the coefficients of a simple linear regression model.

Overview
Gradient Descent is an iterative optimization algorithm used to find the minimum of a function. In the context of linear regression, it is used to minimize the cost function, typically the Mean Squared Error (MSE), to find the optimal parameters (coefficients) that best fit the data.

Mathematical Explanation
Linear Regression Model
The linear regression model can be represented as:

$y = \theta_0 + \theta_1 x$

Where:

$y$ is the dependent variable (target).
$x$ is the independent variable (feature).
$\theta_0$ is the intercept.
$\theta_1$ is the slope (coefficient for the feature).
Cost Function
The cost function (Mean Squared Error) for linear regression is defined as:

$J(\theta_0, \theta_1) = \frac{1}{m} \sum_{i=1}^{m} \left( ( \theta_0 + \theta_1 x_i ) - y_i \right)^2$

Where:

$m$ is the number of training examples.
$x_i$ and $y_i$ are the feature and target for the $i$-th training example.
Gradient Descent
Gradient Descent aims to minimize the cost function by iteratively updating the parameters $\theta_0$ and $\theta_1$ in the direction of the steepest descent.

Gradients
The gradients of the cost function with respect to $\theta_0$ and $\theta_1$ are calculated as follows:

$\frac{\partial J(\theta_0, \theta_1)}{\partial \theta_0} = \frac{2}{m} \sum_{i=1}^{m} \left( ( \theta_0 + \theta_1 x_i ) - y_i \right)$

$\frac{\partial J(\theta_0, \theta_1)}{\partial \theta_1} = \frac{2}{m} \sum_{i=1}^{m} \left( ( \theta_0 + \theta_1 x_i ) - y_i \right) x_i$

Parameter Updates
The parameters are updated using the learning rate ($\alpha$) and the gradients:

$\theta_0 := \theta_0 - \alpha \frac{\partial J(\theta_0, \theta_1)}{\partial \theta_0}$

$\theta_1 := \theta_1 - \alpha \frac{\partial J(\theta_0, \theta_1)}{\partial \theta_1}$

Iterative Process
Initialize Parameters: Start with an initial guess for $\theta_0$ and $\theta_1$.

Compute Gradients: For each training example, compute the residual and update the gradients:

$\text{residual} = ( \theta_0 + \theta_1 x_i ) - y_i$

Update the gradients:

$\text{gradient}_0 += \frac{2}{m} \text{residual}$
$\text{gradient}_1 += \frac{2}{m} \text{residual} \cdot x_i$

Update Parameters: Adjust the parameters using the computed gradients:

$\theta_0 := \theta_0 - \alpha \cdot \text{gradient}_0$
$\theta_1 := \theta_1 - \alpha \cdot \text{gradient}_1$

Repeat: Continue the process for a specified number of iterations.

Summary
This alternative gradient descent algorithm iteratively updates the parameters $\theta_0$ and $\theta_1$ to minimize the cost function and find the best-fit line for the given data. By calculating the gradients based on the residuals of each data point and adjusting the parameters accordingly, the algorithm converges to the optimal coefficients for the linear regression model.
