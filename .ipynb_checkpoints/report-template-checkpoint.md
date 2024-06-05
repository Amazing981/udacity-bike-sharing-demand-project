# Report: Predict Bike Sharing Demand with AutoGluon Solution
Betty Mtengwa

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
When l firstly tried to submit my predictions l encountered an error message saying that the train and test dataset had different columns. Therefore, l could not use the test data for predictions. The train dataset hads 12 columns while test dataset had 9 columns. I had to drop casual and registered columns from the train dataset. These columns did not have an effect on count which is the column we were trying to predict.

### What was the top ranked model that performed?
WeightedEnsemble_L3 had the top ranked model with a score of -30.3320

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
With explolratory data analysis, l was able to check what my data structure looked like. 
I also noticed that there was data imbalance in the columns such as the weather column had 4 categories for results, however the forth category had one entry. Holiday columns also had uneven data distribution.

### How much better did your model preform after adding additional features and why do you think that is?
After adding additional features, the model performance improved and had a score of  0.61315 compared to the previous score of 1.80551. Splitting the datetime feature into multiple independent features allowed the model to assess these variables against the count more effectively.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
After trying different hyperparameters the model had a score of  0.54213. The model had the best score compared to the other two previous models.

### If you were given more time with this dataset, where do you think you would spend more time?
If l had more time, l would spend more time working on the choice of hyperparameters.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|
| model        | hpo1                 | hpo2                 | hpo3                    | score   |
|--------------|----------------------|----------------------|-------------------------|---------|
| initial      | presets:best quality | presets:best quality | presets:best quality    | 1.80551 |
| add_features | Parsing of Dates     | Four columns Added   | optimize_for_deployment | 0.61315 |
| hpo          | Regression           | Regression           | Bagging                 | 0.54213 |

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](img/model_train_score.png)
https://d-hea5rdeev0tp.studio.us-east-1.sagemaker.aws/jupyter/default/files/model_train_score.png?_xsrf=2%7C3a496a7a%7C2f6c91ea3c34029482d2d2c529c866c3%7C1717008972

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](img/model_test_score.png)
https://d-hea5rdeev0tp.studio.us-east-1.sagemaker.aws/jupyter/default/files/model_test_score.png?_xsrf=2%7C3a496a7a%7C2f6c91ea3c34029482d2d2c529c866c3%7C1717008972

## Summary
AutoGluon is used to build machine learning models using a few lines of coding. One of the advantages of using AutoGluon is that it provides a faster model training and deployment thereby achieving a strong predictive performance.

I enjoyed working with AutoGluon on this project due to several reaasons such as
 1. I was able to tune my model by adding hyperparameters with ease.
 2. The training of the model using regression and deployment was achieved by using a few lines of code.
 3. I was able to train the model without doing any feature engineering or data manipulation. This means users can work with raw data and without using any data transformation techniques.
