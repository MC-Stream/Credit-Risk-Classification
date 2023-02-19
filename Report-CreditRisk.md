# Credit Risk Report

## Overview of the Analysis

This notebook will use a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of future borrowers. Testing two different models, it will see if either has a better ability to detect those that might default on their loans. Using machine learning and regression models, we will attempt to teach the computer to predict defaults if given new data it has not seen before.

To do this we used Logistic Regression, which estimates the probability of an event occurring based on a given dataset of independent variables. Feeding the training data into the machine, we can compare that to the test data to see how well the model predicts teh event we want, i.e. default on their loan.

The disadvantage with this though is the difference in the size of the prediction variable. With 750361 non-defaults to 2500 defaults, we decided to adjust the data set via Oversampling to help the model better predict those that might default on their loan. Oversampling is when you notice one class doesn’t have enough instances in the training set, then you choose more instances from that class to do the training. In fact, you resample enough of the original instances to make the size of the smaller class equal to the size of the larger class in the training set. This helps train the model to better understand what it needs to look for in the case of a default.

## Results

As we want the models to accuralely predict possible defaulting clients from data; we use these 3 measures to evaluate our models.

**Accuracy** measures how often the model was correct.
**Precision** measures how confident we are that the model correctly made the predictions.
**Recall** measures the number of actual default transactions that the model correctly classified as default.


* Logistic Regression:
  * Accuracy: 95.2%
  * Precision: 85%
  * Recall: 91%



* Logistic Regression w/ Oversampling:
  * Accuracy: 99.4%
  * Precision: 84%
  * Recall: 99%
  
## Summary


From the above data, we can conclude that the Oversampling allowed the model to better predict if a loan was going to default or not. The Oversampling increased the Accuraccy and the Recall significantly. We noticed a slight loss in precision, but that is normal. A fundamental tension exists between the precision and the recall, so it depends on which of these factors we wish to be more correct.

This will fully depend on what we are trying to achieve here, if we are trying to minimize offering loans to those that might potentially default, then the Oversampling Model appears to offer us a much better option. If we are just trying to lend out the money without worrying too much about defaults (as they are a low occurance at 3.33%), then we can be happy with just the LR Model. Overall, both Models do a great job at having over 95% accuracy and above 90% Recall.

As I feel that we are attempting to reduce our Defaults, I would suggest that we use the Oversampling Model to reduce that possibility.
