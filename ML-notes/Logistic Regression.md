# Logistic Regression

**Contents**

[Log-Odds](#logodds)   

[Sigmoid Function](#sigf)  

[Log Loss](#logloss)  

[Classification Thresholding](#classthre)  

[Scikit-Learn](#sklearn)

-----

Consider an simple data which ```y``` is either 1 (passing), or 0 (failing), and we have one feature, ```num_hours_studied```.
In this example, we want to predict the propability of passing which does not provided by output of **Linear Regression model**. Therefore, we step in **Logistic Regression**.

To predict the probability of a data sample belonging to a class:
1. initialize all feature coefficients and intercept to 0.  
2. multiply each of the feature coefficients by their respective feature value to get what is known as the **log-odds**.  
3. place the log-odds into the **sigmoid function** to link the output to the range [0,1], giving us a probability.  

## Log-Odds <a name="logodds"/>

Calculate the odds of an event occurring as follows:

<img src="http://chart.googleapis.com/chart?cht=tx&chl= Odds = \frac{P(success)}{P(fail)}" >, <img src="http://chart.googleapis.com/chart?cht=tx&chl= log-odds = log( \frac{P(success)}{P(fail)} )" >

Logistic regression model:

<img src="http://chart.googleapis.com/chart?cht=tx&chl= log(\frac{p}{1-p}) = \beta_{0}%2B\beta_{1}x_{1}%2B\cdots%2B\beta_{k}x_{k}" >

Therefore, 

<img src="http://chart.googleapis.com/chart?cht=tx&chl= p = \frac{exp(\beta_{0}%2B\beta_{1}x_{1}%2B\cdots%2B\beta_{k}x_{k})}{1 %2B exp(\beta_{0}%2B\beta_{1}x_{1}%2B\cdots%2B\beta_{k}x_{k})}" > 

which <img src="http://chart.googleapis.com/chart?cht=tx&chl= p" > is the probability of success.

**Python Code:**  
```py
def log_odds(features, coefficients,intercept):
  return np.dot(features,coefficients) + intercept
```

## Sigmoid function <a name="sigf"/>

The Sigmoid Function is a special case of the more general Logistic Function, where Logistic Regression gets its name.

<img src="http://chart.googleapis.com/chart?cht=tx&chl= h(z) = \frac{1}{1 %2B exp(-z)}" >

By plugging the log-odds into the Sigmoid Function, defined below, we map the log-odds to the range [0,1].

**Python Code:**  
```py
def sigmoid(z):
    denominator = 1 + np.exp(-z)
    return 1/denominator
```

## Log Loss <a name="logloss"/>

The loss function for Logistic Regression, known as Log Loss, is given below:

<img src="http://chart.googleapis.com/chart?cht=tx&chl= -\frac{1}{m}\sum_{i=1}^{m}[y^{(i)}log(h(z^{(i)})) %2B (1-y^{(i)})log(1-h(z^{(i)}))]" >

**Python Code:**  
```py
def log_loss(probabilities,actual_class):
  return np.sum(-(1/actual_class.shape[0])*(actual_class*np.log(probabilities) + (1-actual_class)*np.log(1-probabilities)))
 ```
 
## Classification Thresholding <a name="classthre"/>

Many machine learning algorithms, including Logistic Regression, spit out a classification probability as their result. Once we have this probability, we need to make a decision on what class the sample belongs to. This is where the classification threshold comes in. We can choose to change the threshold of classification based on the use-case of our model.  

## Scikit-Learn <a name="sklearn"/>

```py
from sklearn.linear_model import LogisticRegression
model.fit(features, labels)
```
The model is trained, we can access a few useful attributes of the LogisticRegression object.  
* ```model.coef_``` is a vector of the coefficients of each feature  
* ```model.intercept_``` is the intercept   

With our trained model we are able to predict whether new data points belong to the positive class using the ```.predict()``` method! ```.predict()``` takes a matrix of features as a parameter and returns a vector of labels 1 or 0 for each sample.

```py
model.predict(features)
model.predict_proba(features)
```
