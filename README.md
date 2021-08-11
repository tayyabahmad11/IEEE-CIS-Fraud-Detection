# IEEE-CIS-Fraud-Detection

Authors: Tayyab Ahmad, Andrew Grebenisan

A Kaggle competiton hosted by IEEE-CIS. We were supplied a dataset of 1,000,000+ credit card transactions and associated features of each transaction (date/time, amount, type of transaction, category of purchase etc.) with the goal of identifying fraudulent transactions.

To decide what model we would end up using, we considered the pros and cons of different algorithms that we have experience with. We knew that using a logistic regression model or neural network would not perform well due to most of the data being categorical. We considered an SVM but did not end up actually testing with it because from experience, SVMs take incredibly long to train, especially on very large datasets. Additionally, we were aware that tree-based models work much better with categorical data so this seemed the best methodology for this scenario. This thought led us to the LGB classifier. 

As opposed to XGBoost, which grows the tree level-wise, LGB grows the tree leaf-wise, which is computationally more efficient and consumes less memory. Leaf-wise growth also allows for more variance than XGB, but with the max tree depth hyperparameter, we can tune the height so as not to overfit. There are additional regularization methods that allow for the model to become more robust, such as L2 regularization. Thus, our final model that we decided to use was the LightGBM.


