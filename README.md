Nonlinear Regression on Advertising Data
Project Overview
In my previous project, I applied linear regression to the Advertising dataset to predict sales based on advertising budgets.
In this project, I continued working with the same dataset and explored nonlinear regression to investigate whether different nonlinear functions could better capture the relationships between advertising budgets and sales.

Dataset
The dataset contains advertising budgets for three media channels and the corresponding sales:
TV — TV advertising budget
Radio — Radio advertising budget
Newspaper — Newspaper advertising budget
Sales — Target variable

Modeling Approach
1. Exploring the Relationship Between TV and Sales
I started by visualizing the relationship between TV advertising and sales.
The scatter plot suggested a nonlinear pattern, with sales increasing more rapidly at lower TV advertising values and growing more slowly as TV advertising increased.
Based on this observation, I explored different functional forms to model the relationship.

2. Comparing Logarithmic and Square Root Functions
I initially fitted a logarithmic function to the TV advertising data.
After examining the fitted curve, I tested a square root function as an alternative because its shape appeared to better capture the pattern at the beginning of the observed data range.
I compared the functions using model evaluation metrics rather than relying on visual inspection alone.
The square root function achieved better cross-validation performance in my experiments, so I selected it for further modeling.

3. Adding Radio to the Model
Next, I explored the relationship between Radio advertising and sales.
Since the relationship did not appear to follow a clear logarithmic pattern, I tested different polynomial degrees for the Radio component.
I combined the square root TV component with the Radio component to construct a nonlinear regression function.

4. Comparing Polynomial Degrees
I evaluated different polynomial degrees for the Radio component:

Degree 1: Linear Radio component
Degree 2: Quadratic Radio component
Degree 3: Cubic Radio component

I used 5-fold cross-validation to assess how consistently the models performed across different data splits.
I also evaluated the models on a separate test set using the following metrics:

R²
Mean Absolute Error (MAE)
Mean Squared Error (MSE)
Root Mean Squared Error (RMSE)
Mean and standard deviation of cross-validation R² scores

This comparison helped me consider both predictive performance and the consistency of model performance across folds.

5. Evaluating the Newspaper Feature
During the nonlinear modeling experiments, I also investigated whether adding Newspaper advertising improved the model.
The addition did not improve the test R² score, while the training R² increased only slightly.
Based on these results, I excluded Newspaper from the final model to maintain a simpler structure without sacrificing observed test performance.

6. Visualizing the Model

I created a three-dimensional visualization of the fitted model using TV and Radio advertising budgets as input features and Sales as the target variable.
The visualization included the fitted model surface and actual observations from the training and test sets.
This helped me visually inspect how well the model represented the observed data.

Final Model:
The selected model combines:

A square root function for TV advertising
A degree 2 polynomial function for Radio advertising

The final model achieved the following results:
Metric Training Set, TestSetR²: 0.925 ,0.948
MAE: 1.109, 0.923
MSE: 2.021, 1.596
RMSE: 1.422, 1.263 
The model achieved a mean cross-validation R² of 0.912, with a standard deviation of 0.036.

Compared with the previously tested logarithmic model using a degree 2 Radio component, the square root model achieved a higher mean cross-validation R² and a slightly lower test RMSE.
Based on these results, the square root TV component combined with the degree 2 Radio component was selected as the final candidate.

Key Learnings
Through this project, I practiced:
Identifying nonlinear relationships through data visualization
Comparing logarithmic and square root functions
Combining different functional forms in a regression model
Exploring polynomial degrees to represent nonlinear relationships
Evaluating feature contributions
Using cross-validation to assess model stability
Comparing models using multiple evaluation metrics
Selecting a model based on predictive performance and complexity

Conclusion
This project extended my previous linear regression work by exploring nonlinear models on the same Advertising dataset.
By comparing different functional forms and polynomial degrees, I investigated how model structure affects predictive performance.
The final model combined a square root function for TV advertising with a quadratic Radio component. It achieved a test R² of 0.948 and a mean cross-validation R² of 0.912.
This project strengthened my understanding of nonlinear regression, model evaluation, and evidence-based model selection.
