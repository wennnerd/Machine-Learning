# Accuracy, Recall, and Precision

**Contents**

[**Accuracy**](#acc)

[**Recall**](#recall)

[**Precision**](#pre)

-----
Consider that using machine learning algorithm to predict whether or not you will get above a B on a test. Then we have the following feature:  
* The number of hours you studied this week.  
* The number of hours you watched Netflix this week.  
* The time you went to bed the night before the test.  
* Your average in the class before taking the test.  

First, define our terms of grade:  
* True Positive: The algorithm predicted you would get above a B, and you did.
* True Negative: The algorithm predicted you would get below a B, and you did.
* False Positive: The algorithm predicted you would get above a B, and you didn’t.
* False Negative: The algorithm predicted you would get below a B, and you didn’t.

<table>
    <tr>
        <td > </td> 
        <center><td colspan="3">Predict Class</td></center>
   </tr>
    <tr>
        <td rowspan="3">Actual Class</td>
        <td > </td> 
        <td >Positive</td> 
        <td >Negative</td> 
    </tr>
    <tr>
        <td >Positive</td> 
        <td >True Positive</td> 
        <td >False Negative</td> 
    </tr>
    <tr>
        <td >Negative</td>
        <td >False Positive</td>  
        <td >True Negative</td>
    </tr>
</table>

## Accuracy <a name="acc"/>

在所有情況中，正確判斷真假的比例

<img src="http://chart.googleapis.com/chart?cht=tx&chl= \frac{TP \quad + TN}{TP + FN + FP + TN} + " style="border:none;">

## Recall <a name="recall"/>

為真的情況下，有多少被正確判斷出來

## Precision <a name="pre"/>

判斷為真的情況下，有多少是真的真
