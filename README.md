# Machine-Learning

#Building the Model 

Prior to building any models, the training dataset was cleaned by 1) removing all variables that had NA’s present. Each of these variables were missing 97% of the observations, 2) removing all variables that did not contain variation, and 3) removing the first 6 variables because their descriptive names indicated that they would not have predictive power. This reduced the training dataset from containing 159 predictor variables to 5e predictor variables. The variables that were removed from the training dataset were also removed from the testing dataset.

A two possible models were fitted to the training dataset. These models included all variables using the machine learning methods of random forests and partitioning with trees. The gradient boosting algorithm was also going to be considered but it repeatedly crashed my computer so it was omitted from the analysis. Additionally, PCA was going to be considered as a preprocessing method but the accuracy of the random forest algorithm with all the predictors was excellent so PCA was not performed. Model stacking was also going to be performed but since the accuracy of the random forest algorithm was so high, stacking was unnecessary.

#Cross Validation
Cross validation was performed using the holdout method. The training dataset was split into a training set (75% of the observations) and a validation dataset (25% of the observations). The splitting proportions were based on an example used in a class video.

Each of model was fit to the training dataset and the fits were then used to predict the classe variable in the validation dataset. The accuracy for the partitioning with trees (“rpart”) was 49% and for the random forest was 99.2%. The model with the greatest accuracy, the model that applied the random forest machine learning algorithm was selected as the best model for this assignment. 

#Error Estimate
The expected out of sample error is 99%. This error rate is the prediction accuracy of the selected model on the validation data set. Because this is based on the validation dataset, it is likely higher than the actual out of sample error. When the data were split, I thought that the testing dataset would have the correct classe answers so I initially planned to use the testing dataset to determine the out of sample error. However, this dataset did not contain the classes variable so it could not be used for the purposes of an error estimate.  
