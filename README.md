# Final Lab Report
### Daniel Borders (dborder1@jhu.edu)

## Problem Summary
I will be analyzing a red wine data set that has 11 features of wine and corresponding reviews of the wine by critics. The goal is to predict the critics score from the acidity, citric acid, sugar, etc. Becoming a professional wine taster can take years of education, so if we successfully create a model to accurately rate wine from machine producible data, the cost of generating ratings would drastically decrease. [Data set](https://archive.ics.uci.edu/ml/datasets/wine+quality)


## Methods
A fully connected neural network was used to predict the wine ratings from wine properties. A neural network was chosen because none of the co-variances between the wine features and the quality score had a large magnitude. This means that the relationship between features and wine is a deeper, more non-linear relationship. As a result, linear regression was not included.


## Results
A baseline logistic regression approach achieved training accuracy of 59% and testing
accuracy of 58%.

A neural network training accuracy of 69% and testing accuracy 66% were achieved.

A final training/testing accuracy of >=97.5% was achieved if a wiggle room of 1 was allowed. Meaning, the sample was counted correct if it predicted 5 when the truth was 6 for example (Scores are on a 10pt scale).

## Interpretation
Rating wine is a difficult challenge because it is a subjective profession. While one critic my rate a wine 6 the other one may rate it 5. Furthermore, there are no direct correlations between the variables and the quality, meaning the task is highly nonlinear. Non-linearity makes sense in the case of wine. For example, if we looked at citrus acid, adding a ton of citrus acid would make the wine too acidic whereas adding very little would make it not acidic enough. The sweet spot could be where the citric acid matches up to a perfect sugar content to make the perfect acid to sugar ratio. For this reason, the quality is a nonlinear function of all the parameters.

The most challenging part of this problem is the n+1 sensitivity. When we look at the accuracy with a +- 1 tolerance the accuracy is much greater than the accuracy penalizing for n+1 errors.
While the accuracy and precision values are not the best, I believe our model is sufficient because it almost always gets within 1 of the subjective label. As a result, the wine score will reflect the general quality of the wine. That being said, the data set is biased because most
 
values lie in the range 4-7. This means the model will be less likely to predict a 10 because it was not trained on any 10s.

##Potential Improvements
The most valuable improvement would be balancing the data set with more data. Since the data is almost all in the range 4-7 the model is biased. So adding many wines rated in the 1-3 and 8-10 range would greatly improve model performance and generality. Instead of only learning the small details that differentiate a 5 from 6 the model would learn what makes a great or terrible. That way, if the model encountered a terrible wine in the field, it would label it as 1 instead of 5.
In order to reduce the subjectivity of the data, many critics could review the wine and their scores could be averaged. With the current data, the number of classes could be reduced to 5; reducing 1-2 as 0, 3-4 as 1 etc. This would reduce the subjectivity by reducing the number of possible classes.

Other classifiers could be implemented. For example, support vector machines could be an interesting comparison to the more modern neural network.