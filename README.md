# Ensemble Models – A Classification Project Using Random for the Cement Industry

Feature analysis plays a critical role in predicting cement strength, which is a key quality indicator for the cement industry. Cement strength determines its suitability for various applications, directly impacting the safety, durability, and performance of construction projects. This classification project will implement Random Forest, an ensemble algorithm well-suited for regresion tasks.


## Content

1. Objective
2. Business Logic
3. Loading the Dataset
4. Dataset Overview
5. Data Cleanup and Preparation
6. Good Data Practices
7. Missing and Duplicated Values
8. Some Statistics
9. Model Implementation
10. Feature Importance
11. Results and Model Performance
12. Confusion Matrix
13. Actual Vs Predicted Values


## Dataset Description and Dictionary

The dataset contains various features that might impact the strenth of the cement. Below is the detailed data dictionary:

| Feature                 | Type       | Description                                                                 |
|-------------------------|------------|-----------------------------------------------------------------------------|
| `id`                    | Integer    | Unique ID of the mixture                                                   |
| `cement_water`          | Float      | Cement and water quantities in the mixture, separated by a delimiter        |
| `slag`                  | Float      | Slag quantity in the mixture                                               |
| `fly_ash`               | Float      | Fly ash quantity in the mixture                                            |
| `plasticizer`           | Float      | Plasticizer quantity in the mixture                                        |
| `coarse_fine_aggregate` | Float      | Coarse and fine aggregate quantities, separated by a delimiter             |
| `age`                   | Float      | Age of the mixture                                                         |
| `outcome`               | Categorical| The strength of the mixture (0 - low, 1 - high)                            |


## Data Cleanup and Preparation

Data preparation is essential to ensure the dataset is clean, consistent, and ready for analysis. In this project, custom preprocessing functions were implemented to handle the following tasks:

1. Text-to-Number Conversion:
    Converted textual representations of numbers (e.g., "twenty") into numeric values for consistency.

2. Splitting Combined Columns:

    * The cement_water column was split into cement and water for independent analysis.
    * The coarse_fine_aggregate column was divided into coarse and fine aggregates.

3. Error Handling:
    Functions included robust error handling to manage unexpected formats or missing values.

These preprocessing steps ensured the dataset was in a structured and interpretable format, critical for accurate model predictions.


## Acknowledgements

This project is an extension of an original exercise developed for Unosquare, exploring applications in Data Science.


## Random Forest Model Theory

This project implements a **Supervised Learning** model using the **Random Forest** algorithm to classify the target variable (cement strength).

Random Forest is a versatile and robust machine learning algorithm that improves prediction accuracy by creating an ensemble of multiple decision trees. Each tree is trained on a random subset of the data and features, and the algorithm aggregates their predictions to produce a final output. This approach reduces overfitting, enhances generalization, and makes the model highly effective for both classification and regression tasks.

Below are some key parameters of the Random Forest model:

- **n_estimators**:
    Defines the number of decision trees in the forest. A higher number of trees increases the model's stability and accuracy but also raises computational requirements.

- **max_depth**:
    Specifies the maximum depth of each decision tree. Limiting depth controls the model's complexity, helping to prevent overfitting.

- **min_samples_split**:
    Determines the minimum number of samples required to split an internal node. Larger values encourage simpler trees and reduce overfitting.

- **max_features**:
    Controls the number of features considered when splitting a node. This randomness helps ensure diversity among the trees, improving the model’s robustness.


## Results

The Random Forest model proved highly effective for predicting cement strength, achieving an overall accuracy of 91%. This highlights the model's capability to generalize well across both low and high-strength cement mixtures.

Feature importance analysis revealed that `age`, `cement`, `water`, and `plastizicer` are the most influential variables, indicating their importance in determining cement strength. Other features like plasticizer and aggregate composition also contributed, albeit to a lesser extent.

Thorough data preparation, including splitting combined columns and converting textual data into numeric values, was essential for ensuring the dataset's usability. This step streamlined the analysis and contributed directly to the model's strong performance.

The confusion matrix and classification report demonstrated balanced predictions between classes, with high precision and recall scores for both low and high-strength categories. This indicates that the model minimizes bias and performs consistently across the target variable's classes.

This project underscores the potential of machine learning in the cement industry, enabling better quality control, optimization of materials, and cost-effective decision-making for various construction applications.