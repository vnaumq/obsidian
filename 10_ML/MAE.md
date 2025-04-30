[[Loss]]

## Mean Absolute Error (MAE)

#Metric

The average loss per example when [**L1 loss**](https://developers.google.com/machine-learning/glossary#L1_loss) is used. Calculate Mean Absolute Error as follows:

1. Calculate the L1 loss for a batch.
2. Divide the L1 loss by the number of examples in the batch.

![[MAE.png]]
For example, consider the calculation of L1 loss on the following batch of five examples:

|Actual value of example|Model's predicted value|Loss (difference between actual and predicted)|
|---|---|---|
|7|6|1|
|5|4|1|
|8|11|3|
|4|6|2|
|9|8|1|
||   |8 = L1 loss|

So, L1 loss is 8 and the number of examples is 5. Therefore, the Mean Absolute Error is:

Mean Absolute Error = L1 loss / Number of Examples
Mean Absolute Error = 8/5 = 1.6

Contrast Mean Absolute Error with [**Mean Squared Error**](https://developers.google.com/machine-learning/glossary#MSE) and [**Root Mean Squared Error**](https://developers.google.com/machine-learning/glossary#RMSE)
