# DataHack-Numadic
Dataset Link: https://nuws.co/datahack-dataset

data-visualization.ipynb file contains the data visualization tasks performed 

model-training.ipynb file contains training of 3 models, LogisticRegression with GridSearch for tuning of hyperparameters, KNN model and RandomForestClassifier

predictions.ipynb file contains prediction made by Logistic Regression model on test set

1. Random Forsest Classifier model - https://drive.google.com/file/d/1HmoUEDoCtuTg-oec29WS-GxZsj9iM0l3/view?usp=share_link
2. KNN model - https://drive.google.com/file/d/1S4ngHe3KUf3mojegsdxs76we7BAGwpm1/view?usp=share_link
3. Logistic Regression model - https://drive.google.com/file/d/1T7yZPFcf-eG640hzFbxqWccjXBOyFcc1/view?usp=share_link

Why i chose the above 3 models to train and evaluate:
1. Logistic Regression: it is a widely used statistical model for binary classification tasks. It is particularly useful when the relationship between the features and the target variable is assumed to be linear on the log-odds scale. Logistic regression provides interpretable coefficients that can indicate the impact of each feature on the classification outcome
2. KNN (K-Nearest Neighbors): it is a non-parametric classification algorithm that considers the k nearest neighbors to make predictions. KNN does not assume any specific underlying distribution in the data and can handle non-linear relationships effectively. It can be especially useful when there are complex decision boundaries or when the dataset has local patterns.
3. Random Forest: it is an ensemble learning method that combines multiple decision trees to make predictions. Random forest can handle both classification and regression tasks and is known for its robustness against overfitting. Random forest can capture non-linear relationships and interactions between features, and it can handle high-dimensional datasets effectively
4. Considerations for a Large Dataset: the choice of these models is influenced by the characteristics of the large dataset. For logistic regression, it can handle large datasets efficiently and provide interpretable coefficients. KNN can be computationally expensive for large datasets, but its effectiveness in capturing local patterns might still make it a valuable choice. Random forest, despite being computationally intensive, can handle large datasets and provide robust predictions

How these 3 models performed on my dataset:
1. Logistic regression has a relatively simple and fast training process since it involves optimizing a convex loss function. The complexity of the model is low.
2. KNN was computationally expensive, as it requires calculating distances between all pairs of data points, and considering the large size of my dataset the complexity was high
3. Random forest involved training multiple decision trees, which can be computationally expensive, but Random forest is less sensitive to outliers and noise since it aggregates predictions from multiple decision trees

So, in conclusion:
1. Judging based on the evaluation matrix, Logistic Regression model with Grid Search for tuning of hyperparameters gave an accuracy of 91.42% on hold-out test set, with L1 as penalty and C value equal to 1. Random Forest Classifier gave an accuracy of 91.23% and KNN an accuracy of 88.4% with K=1 on the same data
2. I would prefer Logistic Regression model on this data set because of its high accuracy and less computational time

Predictions made by Logistic Regression model on test set: https://drive.google.com/file/d/1UxU2C10pxLuI1EBN67wz_Q0Xk06Jo3yp/view?usp=share_link

Instruction to load the models: 
1. Download the joblib files from the drive link
2. Load them using the code snippet:

from joblib import load

model = load('model_name.joblib')

3. Since the models are trained on a scaled and PCA performed data, it will give better results if the test data fed to it is also scaled and has been performed PCA
