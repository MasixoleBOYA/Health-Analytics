Introduction
In this report, we present the results and interpretation of a linear regression model applied to the "Medical Insurance Charges" dataset. The goal of the analysis was to develop a model using   the linear regression to predict healthcare insurance charges based on various features such as age, gender, BMI, number of children, smoking status, and region of residence. The data set includes information about an individual's healthcare costs, to find out how these costs vary with the given features. The linear regression model serves as a predictive tool to estimate charges and understand the relationships between the predictor variables and the target variable.

Purpose
The objective of regression analysis and its significance is to construct a predictive model that can estimate an individual's medical charges based on their attributes. We can acquire insights into the elements that influence healthcare expenses by examining the relationship between input features and medical charges. This data may be useful to a variety of stakeholders, including healthcare providers, insurers, and legislators.

Data Description:
The dataset utilized for the regression analysis provides information about a group of people's medical bills. Each data entry represents a distinct individual and includes a variety of demographic and healthcare parameters.

Features (Independent Variables):
Age: The individual's age in years (numeric).
Sex: The individual's gender (categorical: female or male).
BMI: Body Mass Index, a numerical measure of body fat based on height and weight.
Children: The number of insured children or dependents (in numbers).
Smoker: Whether the individual smokes (categorical: 'yes' or 'no').
Region: The region in which the individual resides (categorical: southwest, southeast, northwest, northeast) [1].

Dependent Variable (Target Variable):
Charges: The individual's medical expenses (in numbers). This is the variable that we want to predict through regression analysis [1].

In summary, there are six independent factors (age, gender, BMI, children, smoker, and region) and one dependent variable (charges) in the dataset. The purpose of the regression analysis is to create a model that can forecast medical charges properly based on the features provided. We can obtain useful insights into the factors influencing healthcare costs and make educated decisions in the context of healthcare planning and management by studying the relationship between these variables and medical charges.

Data preparation:
Handling missing values: The datasets used for the linear regression did not have any missing values; however, how we would go about handling missing values would be by replacing missing values in the same feature with the mean, median, or mode of the non-missing values. This method is straightforward and suitable for features with a minimal number of missing values.
Encoding Categorical Variables: The code applies one-hot encoding to convert categorical variables (sex, smoker, region) into numerical form. One-hot encoding generates binary columns for each of the original categorical column categories. This is an important step because most machine learning models require numerical inputs and cannot handle categorical variables directly.
StandardScaler: is used to apply feature scaling to the continuous variables age and bmi. The data is transformed by StandardScaler so that it has a mean of 0 and a standard deviation of 1. This ensures that all features are on the same scale, avoiding bigger magnitude features from dominating the learning process of the model.
Train-Test-Split: The test size was set to 0.2, indicating that only 20% of the datasets will be used for testing and 80% for training. The random state was set to 42 to ensure split repeatability for the same split to be obtained each time the code is executed. The training set is used to train machine learning models, while the testing set is used to assess their performance on unknown data. This method evaluates how effectively models generalize to new data and avoids overfitting to the training set.

Methodology:
Three types of regression algorithms are used in the dataset: linear regression, ridge regression, and lasso regression. The following explains each one and their mathematical formulations:
Regression Linear (No Regularization):
Linear Regression is a simple and extensively used regression procedure that fits a linear equation to the observed data to represent the connection between the dependent variable (goal variable) and one or more independent variables (features). A simple linear regression with a single independent variable has the following mathematical formulation:

y =    [2]
 
Where:

y is the dependent variable (target variable).
 is the independent variable (feature).
 is the y-intercept or the value of y when x is 0.
 is the slope or coefficient of the independent variable, representing the change in y for a one-unit change in x.
The goal of linear regression is to find the best-fitting line (linear equation) that minimizes the sum of the squared differences between the observed values and the predicted values.

Ridge Regression (L2 Regularization): Ridge Regression is a linear regression extension that incorporates L2 regularization. Regularization is a technique that adds a penalty term to the loss function to prevent overfitting. The total of the squared coefficients is contributed to the least squares loss function in Ridge Regression. Ridge Regression has the following mathematical formula:

Loss function = [2]

                        

Where:

λ (lambda) is the regularization parameter that controls the strength of regularization. A higher value of λ will shrink the coefficients more, reducing model complexity.
Ridge Regression helps to handle multicollinearity in the data and can improve the generalization performance of the model.

 Lasso Regression (L1 Regularization): Lasso Regression is a linear regression extension that incorporates L1 regularization. Lasso Regression, like Ridge Regression, adds a penalty element to the loss function. Lasso, on the other hand, employs the absolute sum of the coefficients rather than the squared sum. The mathematical formula for Lasso Regression is as follows:

Loss function =      [2]

Where:

λ (lambda) is the regularization parameter that controls the strength of regularization.
Lasso Regression has the property of performing feature selection by setting some coefficients to exactly zero. It can be useful when dealing with high-dimensional datasets with many irrelevant or redundant features.
 Regression Analysis Assumptions:
Linearity: It is assumed that the connection between the dependent variable and the independent variables is linear [3].
Independence: It is presumed that observations are independent of one another [3].
Homoscedasticity means that the error variance is constant across all levels of the independent variables [3].
Normality: It is assumed that the errors are naturally distributed [3].

Model Evaluation:
1. Linear Regression:
Mean Squared Error (MSE): 33596915.85
R-squared (R2): 0.7836
The Linear Regression model has an R-squared value of approximately 0.7836 and a mean squared error of approximately 33,596,915.85. The R-squared result shows that the model's characteristics can explain about 78.36% of the variance in the target variable (charges). The model's performance in predicting the target variable improves as the mean squared error and R-squared value decrease.
2. Ridge Regression:
Mean Squared Error (MSE): 33645306.52
R-squared (R2): 0.7833
Best Alpha: 1.0
The Ridge Regression model has a mean squared error of approximately 33,645,306.52 and an R-squared value of approximately 0.7833, with the best alpha value of 1.0. R-squared is slightly lower than R-squared for Linear Regression, indicating a little poorer fit to the data. Ridge Regression utilizes L2 regularization, which discourages overfitting by charging large coefficient values. The chosen alpha value implies that some regularization is used in the model, however, it may not have a substantial impact on the model's performance when compared to Linear Regression.
3. Lasso Regression:
Mean Squared Error (MSE): 33605625.91
R-squared (R2): 0.7835
Best Alpha: 10.0

The Lasso Regression model has a mean squared error of approximately 33,605,625.91 and an R-squared value of approximately 0.7835, with the greatest alpha value of 10.0. L1 regularization is introduced in Lasso Regression, which not only prevents overfitting but also performs feature selection by reducing some coefficients to absolutely zero. The chosen alpha value implies that the model uses more regularization than Ridge Regression. Despite this additional regularization, the model's R-squared value is comparable to Linear Regression, indicating that it is competitive.

These three models (Linear, Ridge, and Lasso Regression) were used as they appear to produce comparable results, however, the Lasso Regression had quite a lower MSE and R-squared value when compared to the Linear and Ridge Regression. Therefore, its application to this dataset seems to show that applying either L2 (Ridge) or L1 (Lasso) regularization did not significantly increase linear regression performance in comparison to using only linear regression (without regularization). All three approaches (Linear Regression, Ridge Regression, and Lasso Regression) can be said to have very comparable metrics. The optimum model can be determined by other aspects such as interpretability and feature selection requirements, as Lasso Regression may be preferable when looking for a more interpretable model with less relevant characteristics. All models, however, appear to capture a considerable percentage of the volatility in the target variable and perform reasonably well on this dataset.

Tuning Hyperparameters:
Grid Search (GridSearchCV) was used to optimize the hyperparameters (alpha parameter) of Ridge and Lasso Regression models. The optimum hyperparameter values are then utilized to retrain the Ridge and Lasso models [4].

Predicted Vs Actual plots:

Medical Charges vs. BMI:
This scatter plot shows the relationship between medical charges and BMI, coloured by smoker status.
Smokers generally exhibit higher medical charges across varying BMI levels.
The plot indicates that both BMI and smoking status play roles in determining medical charges.

Medical Charges vs Age: 
The scatter plot of medical charges against age, differentiated by smoker status, reveals several patterns.
Smokers tend to have higher medical charges compared to non-smokers, regardless of age.
There is a general trend of increasing charges with age, with a steeper increase for smokers.
This visualization suggests that age and smoking status are important factors affecting medical charges.




Medical Charges by Gender:
The box plot comparing medical charges for different genders suggests that gender alone might not be a strong determinant of charges.
The distribution of charges appears similar for both genders.
There is anomalous data points that are separated from the main data cluster for both genders.











Medical Charges by Smoking Status:
The box plot comparing charges for smokers and non-smokers reveals a significant difference.
Smokers tend to have considerably higher medical charges than non-smokers.
There are anomalous data points that are separated from the main data cluster for non smokers.













Correlation Matrix Plot:




In a summative view of the exploration of the above data, the significant difference in medical charges between smokers and non-smokers indicates that smoking status is a strong predictor of medical charges. While the impact of age on medical charges is evident, especially among smokers who experience a steeper increase in charges as age increases. The distribution of charges by gender also seems relatively consistent, suggesting that gender alone might not be a dominant factor in determining charges. The visualization of BMI and charges on the hand implies that while there is no strong linear relationship, the interaction with smoking status might play a role in determining charges. Thus, the figures from data exploration provide a deeper understanding of how different variables relate to medical charges. Smoking status, age, and BMI emerge as critical factors influencing medical charges. These insights can guide feature selection during model development and help create more accurate predictive models.
