# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Matheus Ribeiro Cerqueira

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
That I do not need to send the model itself but a comma separated values file containing the 'datetime' feature and model predictions. As Kaggle does not accepts values lower than 0 values from predictions lower than 0 were replaced by 0.

### What was the top ranked model that performed?
The top model in every step was the WeightedEnsemble_L3 model. 

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
The histogram shows that the temp, atemp, and humidity features resemble bell shapes. The windspeed and count distribution are skewed to the right and the other features do not have a well-done shape. To improve the model performance the datetime feature was split into day, month, and hour features. By doing that, the model performance score improved from 1.79702 to 0.57313. The evaluation was done by using the root_mean_squared_error metric 

### How much better did your model preform after adding additional features and why do you think that is?
The model performance score improved from 1.79702 to 0.57313. Add relevant and useful features gives the model more information about the relationships between the features and the target variable.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
The model did not get better by using hyperparameters optimization as expected but that is not something abnormal actually the hyperparameter optimization can lead the model to perform better or worst and that is one of the challenges of the hyperparameters optimization process. One way to solve this would be testing with different values until the model performance gets better.

### If you were given more time with this dataset, where do you think you would spend more time?
In the hyperparameter optimization as I get a better score by using models specific hyperparameters

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|num_bag_folds|num_bag_sets|num_stack_levels|models_hyperparameter_status|score|
|--|--|--|--|--|--|
|initial|0|20|0|default|1.79702|
|add_features|0|20|0|default|0.57313|
|hpo|10|30|2|default|0.58625|
|hpo_models|10|30|2|custom|0.53222|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](https://github.com/punkmic/Predict-Bike-Sharing-Demand-with-AutoGluon/blob/48e29c1c003c09aabe25c45dc9060f78c44c3611/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](https://github.com/punkmic/Predict-Bike-Sharing-Demand-with-AutoGluon/blob/b4a2f9786032388b39c5a2b668b67f1ed73dacb8/model_test_score.png)

## Summary
In this study, a machine learning model was developed for predicting [bike sharing demand](https://www.kaggle.com/competitions/bike-sharing-demand/overview) using autogluon, a library for automated machine learning. A regression model was first trained on the original train dataset, then on a dataset with additional features, with hyperparameters optimization, and with model-specific hyperparameters optimization. The model trained on the dataset with additional features had a significant score improvement from 1.79702 to 0.57313 on Kaggle. Despite positive expectations about the hyperparameter optimization, the model had a worse score, but using a model-specific hyperparameter optimization improved the model score from 0.57313 to 0.53222. This result demonstrates that spending more time on hyperparameter optimization could improve the model even better. 
