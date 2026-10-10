Nonlinear Regression on Advertising Data
Project Overview

In my previous project, I applied linear regression to the Advertising dataset to predict sales based on advertising budgets.
In this project, I continued working with the same dataset and explored nonlinear regression to investigate whether a nonlinear model could better capture the relationship between advertising budgets and sales.
Dataset
The dataset contains advertising budgets for three media channels and the corresponding sales:
TV — TV advertising budget
Radio — Radio advertising budget
Newspaper — Newspaper advertising budget
Sales — Target variable

Modeling Approach
1. Exploring the Relationship Between TV and Sales
I started by plotting TV advertising against sales to examine their relationship.
The scatter plot suggested a nonlinear pattern that appeared approximately logarithmic. Based on this observation, I explored a logarithmic function to model the relationship between TV advertising and sales.

2. Building a Logarithmic Model
I fitted a logarithmic function to the training data and evaluated its predictive performance.
This step helped me investigate whether a logarithmic transformation could capture the relationship between TV advertising and sales more effectively.

3. Adding Radio to the Model
Next, I explored the relationship between Radio advertising and sales.
Since the relationship did not appear to follow a clear logarithmic pattern, I tested different polynomial degrees for the Radio component.
I combined the logarithmic TV component with the Radio component to build a nonlinear regression function.

4. Comparing Polynomial Degrees
I evaluated three versions of the model by changing the polynomial degree of the Radio component:

Degree 1: Linear Radio component
Degree 2: Quadratic Radio component
Degree 3: Cubic Radio component

To compare the models, I used 5-fold cross-validation and evaluated their performance on a separate test set.
The evaluation metrics included:

R²
Mean Absolute Error (MAE)
Mean Squared Error (MSE)
Root Mean Squared Error (RMSE)
Mean and standard deviation of cross-validation R² scores

This comparison helped me examine not only prediction accuracy but also the consistency of model performance across different folds.

5. Evaluating the Newspaper Feature
I also tested whether adding Newspaper advertising to the nonlinear model improved its performance.
The addition did not improve the test R² score, while the training R² increased only slightly.
Therefore, I excluded Newspaper from the final nonlinear model to keep the model simpler without sacrificing the observed test performance.

6. Visualizing the Model
I used a three-dimensional plot to visualize the fitted model alongside the actual data points from the training and test sets.
This visualization helped me examine how the model's predicted sales compared with the observed sales across different TV and Radio advertising budgets.

Final Model Selection
Although the degree 3 model achieved the lowest test errors, its mean cross-validation R² was lower and its standard deviation was higher.
The degree 1 model showed slightly more consistent cross-validation performance but had higher test errors.
The degree 2 model provided a reasonable balance between predictive performance, cross-validation consistency, and model complexity.
Based on these results, I selected the degree 2 model as a practical final candidate.

Key Learnings:
Through this project, I practiced:
Identifying potential nonlinear relationships through visualization
Exploring logarithmic and polynomial functions
Combining different functional forms into a single regression model
Comparing models with different levels of complexity
Using cross-validation to assess performance consistency
Evaluating models with multiple regression metrics
Making model-selection decisions based on both predictive performance and complexity

Conclusion

This project extended my previous linear regression work by exploring nonlinear relationships in the same Advertising dataset.
The process involved examining data patterns, constructing and comparing nonlinear functions, evaluating the contribution of an additional feature, and selecting a model based on its predictive performance and cross-validation results.
The project helped me better understand how model structure influences prediction accuracy and why selecting a model requires more than simply choosing the highest test R² score.
