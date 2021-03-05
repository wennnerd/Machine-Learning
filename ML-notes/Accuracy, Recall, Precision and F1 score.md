# Accuracy, Recall, Precision and F1 score

**Contents**

[**Accuracy**](#acc)

[**Recall**](#recall)

[**Precision**](#pre)

[**F1 Score**](#f1)

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

<img src="http://chart.googleapis.com/chart?cht=tx&chl= accuracy = \frac{TP %2B TN}{TP %2B FN %2B FP %2B TN} + " >

## Recall <a name="recall"/>

為真的情況下，有多少被正確判斷出來

<img src="http://chart.googleapis.com/chart?cht=tx&chl= recall = \frac{TP}{TP %2B FN} + " >

## Precision <a name="pre"/>

判斷為真的情況下，有多少是真的真

<img src="http://chart.googleapis.com/chart?cht=tx&chl= precision = \frac{TP}{TP %2B FP} + " >

## F1 score <a name="f1"/>

如果今天我覺得Precision和Recall都同等重要，我想要用一個指標來統合標誌它，這就是F1 Score

<img src="http://chart.googleapis.com/chart?cht=tx&chl= F1 = 2*\frac{Precision*Recall}{Precision%2BRecall}" >
