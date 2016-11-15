# Machine-Learning Assignment

#Building the Model 

Prior to building any models, the training dataset was cleaned by 1) removing all variables that had NA’s present. Each of these variables were missing 97% of the observations, 2) removing all variables that did not contain variation, and 3) removing the first 6 variables because their descriptive names indicated that they would not have predictive power. This reduced the training dataset from containing 159 predictor variables to 52 predictor variables. The variables that were removed from the training dataset were also removed from the testing dataset.

Two possible models were fitted to the training dataset. These models included all variables using the machine learning methods of random forests and partitioning with trees. The gradient boosting algorithm was also going to be considered but it repeatedly crashed my computer so it was omitted from the analysis. Additionally, PCA was going to be considered as a preprocessing method but the accuracy of the random forest algorithm with all the predictors was excellent so PCA was not performed. Model stacking was also going to be performed but since the accuracy of the random forest algorithm was so high, stacking was unnecessary.

#Cross Validation
Cross validation was performed using the holdout method. The training dataset was split into a training set (75% of the observations) and a validation dataset (25% of the observations). The splitting proportions were based on an example used in a class video.

Each of model was fit to the training dataset and the fits were then used to predict the classe variable in the validation dataset. The accuracy for the partitioning with trees (“rpart”) was 49% and for the random forest was 99.2%. The model with the greatest accuracy applied the random forest machine learning algorithm and was selected as the best model for this assignment. 

#Error Estimate
The expected out of sample error is 99%. This error rate is the prediction accuracy of the selected model on the validation data set. Because the error estimate was based on the same data that the model was selected on, the error is likely higher than the actual out of sample error. The intention was to use the testing dataset to produce the error estimate however, the testing dataset did not contain the classe variable so it could not be used for the purposes of an error estimate.  
