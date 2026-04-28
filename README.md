# Project README: Supervised Machine Learning with Iris Dataset

## Overview
This project demonstrates a basic supervised machine learning workflow using the classic Iris dataset. The primary goal is to classify iris species (Setosa, Versicolor, Virginica) based on their sepal and petal measurements. We explore the dataset, train a K-Nearest Neighbors (KNN) classifier, evaluate its performance, and visualize its decision boundaries. A brief comparison with Logistic Regression is also included.

## Dataset
The project utilizes the Iris dataset, a multivariate dataset introduced by Ronald Fisher in 1936. It consists of 150 samples from three species of Iris (Iris setosa, Iris virginica and Iris versicolor), with four features measured in centimeters:

*   `sepal length (cm)`
*   `sepal width (cm)`
*   `petal length (cm)`
*   `petal width (cm)`

The target variable `species` is represented by integers (0, 1, 2) corresponding to 'setosa', 'versicolor', and 'virginica'.

## Methodology

1.  **Data Loading and Initial Exploration**
    *   The Iris dataset is loaded using `sklearn.datasets.load_iris`.
    *   It is then converted into a Pandas DataFrame for easier manipulation.
    *   Basic information such as the shape of the data, feature names, target labels, and data types are displayed.

2.  **Data Splitting**
    *   The dataset is split into training and testing sets using `train_test_split` with an 80/20 ratio and `random_state=42` for reproducibility. This ensures that the model is evaluated on unseen data.

3.  **Model Training (K-Nearest Neighbors)**
    *   A K-Nearest Neighbors (KNN) classifier is initialized with `n_neighbors=3`.
    *   The model is trained on the `X_train` (features) and `y_train` (target) data.
    *   KNN was chosen due to the dataset's clear, distance-separable clusters, which makes it well-suited for this algorithm.

4.  **Model Evaluation**
    *   The trained model predicts species on the `X_test` data.
    *   Performance is assessed using `accuracy_score` and a `confusion_matrix`.
    *   The confusion matrix is visualized using `seaborn.heatmap` to show correct and incorrect classifications.

5.  **Interpretation of Results**
    *   The KNN model often achieves 100% accuracy on the Iris dataset, particularly with a `random_state=42` during splitting. This high accuracy is attributed to the dataset's high separability, especially for the Setosa species.
    *   The confusion matrix typically shows perfect classification, with all samples correctly placed on the diagonal.

6.  **Visualizing Decision Boundaries**
    *   To illustrate how the KNN model classifies, decision boundaries are plotted.
    *   For simplicity in visualization, the model is re-trained using only two features: 'petal length (cm)' and 'petal width (cm)'.
    *   `DecisionBoundaryDisplay` from `sklearn.inspection` is used to visualize the regions where the model predicts each species.

7.  **Comparison with Logistic Regression (Bonus)**
    *   A Logistic Regression model is also trained and evaluated on the same split data.
    *   Its accuracy is compared against the KNN model to provide a comparative insight into different classification approaches for this dataset.

## Key Findings
*   The K-Nearest Neighbors model demonstrated exceptional performance, achieving 100% accuracy on the test set of the Iris dataset.
*   The confusion matrix confirmed zero misclassifications, indicating a perfect separation of the iris species by the model.
*   The Iris dataset's inherent separability allows even relatively simple models like KNN to achieve optimal performance.
*   Both KNN and Logistic Regression performed very well on this dataset, with KNN creating more 
