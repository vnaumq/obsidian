[[Linear regression]]

[**Gradient descent**](https://developers.google.com/machine-learning/glossary#gradient-descent) is a mathematical technique that iteratively finds the weights and bias that produce the model with the lowest loss. Gradient descent finds the best weight and bias by repeating the following process for a number of user-defined iterations.

The model begins training with randomized weights and biases near zero, and then repeats the following steps:

1. Calculate the loss with the current weight and bias.
    
2. Determine the direction to move the weights and bias that reduce loss.
    
3. Move the weight and bias values a small amount in the direction that reduces loss.
    
4. Return to step one and repeat the process until the model can't reduce the loss any further.
    

The diagram below outlines the iterative steps gradient descent performs to find the weights and bias that produce the model with the lowest loss.
![[gradient-descent.png]]
## Model convergence and loss curves

When training a model, you'll often look at a [**loss curve**](https://developers.google.com/machine-learning/glossary#loss-curve) to determine if the model has [**converged**](https://developers.google.com/machine-learning/glossary#convergence). The loss curve shows how the loss changes as the model trains. The following is what a typical loss curve looks like. Loss is on the y-axis and iterations are on the x-axis:
![[convergence.png]]

You can see that loss dramatically decreases during the first few iterations, then gradually decreases before flattening out around the 1,000th-iteration mark. After 1,000 iterations, we can be mostly certain that the model has converged.

In the following figures, we draw the model at three points during the training process: the beginning, the middle, and the end. Visualizing the model's state at snapshots during the training process solidifies the link between updating the weights and bias, reducing loss, and model convergence.

In the figures, we use the derived weights and bias at a particular iteration to represent the model. In the graph with the data points and the model snapshot, blue loss lines from the model to the data points show the amount of loss. The longer the lines, the more loss there is.

In the following figure, we can see that around the second iteration the model would not be good at making predictions because of the high amount of loss.
![[large-loss.png]]
At around the 400th-iteration, we can see that gradient descent has found the weight and bias that produce a better model.
![[med-loss.png]]

And at around the 1,000th-iteration, we can see that the model has converged, producing a model with the lowest possible loss.
![[low-loss.png]]
### Convergence and convex functions

The loss functions for linear models always produce a [**convex**](https://developers.google.com/machine-learning/glossary#convex-function) surface. As a result of this property, when a linear regression model converges, we know the model has found the weights and bias that produce the lowest loss.

If we graph the loss surface for a model with one feature, we can see its convex shape. The following is the loss surface of the miles per gallon dataset used in the previous examples. Weight is on the x-axis, bias is on the y-axis, and loss is on the z-axis:
![[convexity.png]]
