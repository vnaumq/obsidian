[[ML models]]

[**Linear regression**](https://developers.google.com/machine-learning/glossary#linear-regression) is a statistical technique used to find the relationship between variables. In an ML context, linear regression finds the relationship between [**features**](https://developers.google.com/machine-learning/glossary#feature) and a [**label**](https://developers.google.com/machine-learning/glossary#label).

For example, suppose we want to predict a car's fuel efficiency in miles per gallon based on how heavy the car is, and we have the following dataset:
![[car-data-points.png]]

We could create our own model by drawing a best fit line through the points:
![[car-data-points-with-model.png]]

## Linear regression equation

In algebraic terms, the model would be defined as , where

-  is miles per gallon—the value we want to predict.
-  is the slope of the line.
-  is pounds—our input value.
-  is the y-intercept.

In ML, we write the equation for a linear regression model as follows:

where:

-  is the predicted label—the output.
-  is the [**bias**](https://developers.google.com/machine-learning/glossary#bias-math-or-bias-term) of the model. Bias is the same concept as the y-intercept in the algebraic equation for a line. In ML, bias is sometimes referred to as . Bias is a [**parameter**](https://developers.google.com/machine-learning/glossary#parameter) of the model and is calculated during training.
-  is the [**weight**](https://developers.google.com/machine-learning/glossary#weight) of the feature. Weight is the same concept as the slope  in the algebraic equation for a line. Weight is a [**parameter**](https://developers.google.com/machine-learning/glossary#parameter) of the model and is calculated during training.
-  is a [**feature**](https://developers.google.com/machine-learning/glossary#feature)—the input.

During training, the model calculates the weight and bias that produce the best model.

![[equation.png]]

### Models with multiple features

Although the example in this section uses only one feature—the heaviness of the car—a more sophisticated model might rely on multiple features, each having a separate weight (, , etc.). For example, a model that relies on five features would be written as follows:

For example, a model that predicts gas mileage could additionally use features such as the following:

- Engine displacement
- Acceleration
- Number of cylinders
- Horsepower

This model would be written as follows:
![[equation-multiple-features.png]]

