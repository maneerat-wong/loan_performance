# loan_performance
Personal project on loan performance analysis 

The purpose of this project is to explore the likelihood of good loan and bad loan in each lender from the loan performance data as a lending company.Therefore, I want to explore the factors of people paying or not paying the loan and conduct the model to predict whether my future borrowers are going to pay the loan.

This data set is quite challanging because I've never train the model for the highly imbalanced data  before. The ratio of good and bad loan is 5:95 but it's quite common for the data like this (similar to the fraud detection)

## Data Exploration
- Interest rate has the highest association with the loan type which means that the higher the interest rate, the higher chance that the loan will become a bad loan. However, the correlation score between interest rate and loan type  is not that high(less than 0.5) so the distribution between two groups is not significantly different.
- The outstanding principal has a negative correlation towards the loan type.

## Prediction Model
The data set is splitted to be the train and test data set in 80:20 ratio and it will also be scale to unit variance by using StandardScaler
The matrix to use for model evaluation are
1.Score
2.F1 socre
3.Area under curve score
4.Confusion Matrix
5.Precision recall curve

|                      | Score  | F1 Score | Area under curve score |
|----------------------|--------|----------|------------------------|
| Random Forest        | 0.9768 | 0.631578 | 0.730769               |
| Decision Tree        | 0.9437 | 0.439560 | 0.737977               |
| Deep Learning(Keras) | 0.9636 | 0.266666 | 0.797198               |

Even though the scores of all models are very good, the f1 score is not that good. This is very important for binary classifiers as we care the most on the True positive and False positive. We don’t want to give the loan to the borrower who is likely to turn it to the bad loan so the False positive need to be very low ( compared to the True positive ) Random Forest seems to be the most promising model.

## Next Step
In order to improve the prediction score or find more significant insight, I think I should focus more on feature engineering, for example,using permutation importance technique as a starter point to explore more on the features.
