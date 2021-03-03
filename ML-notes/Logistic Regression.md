# Logistic Regression

Consider an simple data which ```y``` is either 1 (passing), or 0 (failing), and we have one feature, ```num_hours_studied```.
In this example, we want to predict the propability of passing which does not provided by output of **Linear Regression model**. Therefore, we step in **Logistic Regression**.

To predict the probability of a data sample belonging to a class:
1. initialize all feature coefficients and intercept to 0.  
2. multiply each of the feature coefficients by their respective feature value to get what is known as the **log-odds**.  
3. place the log-odds into the sigmoid function to link the output to the range [0,1], giving us a probability.  
