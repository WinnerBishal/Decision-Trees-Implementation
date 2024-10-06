# Obesity Diagnosis Using Decision Trees

## Overview

This project focuses on diagnosing obesity levels in individuals using classification techniques and a Decision Support System (DSS). The dataset used is from the UCI Machine Learning Repository and includes data on various lifestyle and physical factors from individuals in Mexico, Peru, and Colombia. The project aims to classify obesity levels based on these factors and create a rule-based system for diagnosing obesity.

## Goal of the Project

1. Implement classification on the obesity dataset using a Decision Tree Classifier.
2. Explore how different hyperparameters affect the accuracy of the classification model.
3. Derive rules from the classification results to create a Decision Support System (DSS).
4. Predict obesity levels based on key attributes using the DSS.

## Dataset

The dataset includes information on 2111 individuals and contains 17 attributes. These attributes describe eating habits, physical conditions, and demographic information such as:

- **Frequent consumption of high caloric food (FAVC)**
- **Frequency of consumption of vegetables (FCVC)**
- **Number of main meals (NCP)**
- **Consumption of food between meals (CAEC)**
- **Daily water consumption (CH20)**
- **Alcohol consumption (CALC)**
- **Physical activity frequency (FAF)**
- **Time using technology devices (TUE)**
- **Transportation used (MTRANS)**
- **Gender, Age, Height, Weight**

### Classification Targets:
- **Original Targets (7 classes):** Broad classification of obesity, overweight, underweight, and normal weight.
- **Modified Targets (3 classes):** Consolidated into `Obesity`, `Overweight`, and `No Obesity`.

## Methodology

### Data Preparation
- Categorical columns were encoded using `LabelEncoder`.
- Numeric columns were not scaled to retain raw physical measurements.

### Classifier Runs:
1. **Run 1** (`criterion = gini`, `ccp_alpha = 0.01`): The decision tree was pruned to reduce complexity, while maintaining accuracy.
2. **Run 2** (`max_depth = 10`): A larger tree was used, which increased accuracy but also made the tree more complex.
3. **Run 3** (`criterion = entropy`, `ccp_alpha = 0.01`, `max_leaf_nodes = 8`): A pruned tree with specific constraints, leading to a balance between complexity and accuracy.
4. **Run 4** (`max_depth = 4`, `max_leaf_nodes = 6`): A simpler tree with fewer nodes, allowing for clearer rules to be derived.

### Decision Support System (DSS)
Based on the selected decision tree, a set of rules was derived manually. These rules were implemented in the DSS to predict obesity levels in individuals based on input attributes.

## Results

- **Accuracy:** The decision trees achieved up to 97% accuracy, with the best results being obtained using only the height and weight attributes.
- **Key Findings:** Weight and height were the most influential factors in diagnosing obesity. Increasing `max_depth` and `max_leaf_nodes` improved accuracy, but also increased the tree’s complexity. Pruning with `ccp_alpha` helped achieve high accuracy while maintaining simplicity.
- **Conclusion:** Decision Tree Classifiers are effective tools for predicting obesity levels and can be used to derive simple, interpretable rules for diagnosis.

## Conclusion

Decision Trees provide a powerful method for classifying obesity levels and can form the basis of a simple but effective DSS. By tuning hyperparameters like `max_depth`, `max_leaf_nodes`, and `ccp_alpha`, we were able to create models that balance complexity and accuracy. This project demonstrates how such techniques can be applied to real-world health data.

## Thank You!

