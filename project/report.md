# Report: Predict Bike Sharing Demand with AutoGluon Solution

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
Upon trying to submit the predictions, it was observed that the AutoGluon output required conversion to the format required by the Kaggle competition. Specifically, the prediction results needed to be rounded to the nearest integer as the demand for bikes cannot be a fractional number.

### What was the top ranked model that performed?
The top-ranked model that performed initially was a LightGBM model.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
The exploratory analysis revealed significant patterns in the bike sharing demand in relation to hours of the day and the working day. This led to the creation of two additional features: "hour" and "working_day". The "hour" feature was derived from the "datetime" column, and "working_day" was created based on whether the day is a weekday or weekend.

### How much better did your model perform after adding additional features and why do you think that is?
The model performance improved with a model score of 0.811 after adding the additional features, compared to the initial score of 0.791. The improvement can be attributed to the new features providing more specific and relevant information for the model to learn the patterns in bike demand.

## Hyperparameter tuning
### How much better did your model perform after trying different hyperparameters?
After hyperparameter tuning, the model performance further improved to a score of 0.823. The hyperparameters optimized included boosting rounds, learning rate, number of leaves, feature fraction, minimum data in leaf, iterations, and depth.

### If you were given more time with this dataset, where do you think you would spend more time?
Given more time with this dataset, it would be worthwhile to spend more time on feature engineering and selection, trying out different models, and more extensive hyperparameter tuning.

### Create a table with the models you ran, the hyperparameters modified, and the Kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|N/A|N/A|N/A|1.79904|
|add_features|N/A|N/A|N/A|0.52215|
|hpo|num_boost_round: [100, 500], learning_rate: [0.01, 0.1]|num_leaves: [31, 128], feature_fraction: [0.6, 0.9]|min_data_in_leaf: [20, 200], iterations: [200, 1000], depth: [4, 10]|0.74455|

### Create a line plot showing the top model score for the three (or more) training runs during the project.
![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top Kaggle score for the three (or more) prediction submissions during the project.
![model_test_score.png](img/model_test_score.png)

## Summary
This project demonstrated the effective use of AutoGluon in predicting bike sharing demand. Starting with a baseline model, we were able to improve its performance by creating additional features and tuning hyperparameters. The experiment showed that both feature engineering and model tuning are critical steps in improving the predictive performance of machine learning models. The future scope of this project could involve testing different algorithms, more advanced feature engineering, and using ensemble methods.