[[Loss]]

The average loss per example when [**L2 loss**](https://developers.google.com/machine-learning/glossary#L2_loss) is used. Calculate Mean Squared Error as follows:

1. Calculate the L2 loss for a batch.
2. Divide the L2 loss by the number of examples in the batch.

![[MSE.png]]

For example, consider the loss on the following batch of five examples:

|Actual value|Model's prediction|Loss|Squared loss|
|---|---|---|---|
|7|6|1|1|
|5|4|1|1|
|8|11|3|9|
|4|6|2|4|
|9|8|1|1|
||   |   |16 = L2 loss|

Therefore, the Mean Squared Error is:

Mean Squared Error = L2 loss / Number of Examples
Mean Squared Error = 16/5 = 3.2

Mean Squared Error is a popular training [**optimizer**](https://developers.google.com/machine-learning/glossary#optimizer), particularly for [**linear regression**](https://developers.google.com/machine-learning/glossary#linear_regression).

Contrast Mean Squared Error with [**Mean Absolute Error**](https://developers.google.com/machine-learning/glossary#MAE) and [**Root Mean Squared Error**](https://developers.google.com/machine-learning/glossary#RMSE).

[**TensorFlow Playground**](https://developers.google.com/machine-learning/glossary#TensorFlow_Playground) uses Mean Squared Error to calculate loss values.