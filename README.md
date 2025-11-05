# Weight Lifting Exercise Prediction Project  
**Author:** Haider Ali  
**Course:** Practical Machine Learning (Coursera)  
**Instructor:** Johns Hopkins University  

---

## Abstract
This project aims to predict how individuals perform barbell lifts based on sensor data collected from accelerometers placed on the belt, forearm, arm, and dumbbell of six participants. The prediction target is the **"classe"** variable, representing five different execution styles (A–E). A supervised machine learning approach was employed using the Random Forest and Gradient Boosting algorithms to identify the best-performing model. The analysis focuses on data preprocessing, feature selection, model training, cross-validation, and out-of-sample error estimation.

---

## Introduction
In recent years, wearable devices such as the Fitbit, Nike FuelBand, and Jawbone Up have revolutionised personal fitness tracking. While most individuals measure **how much** activity they perform, relatively few quantify **how well** they perform it. This study leverages the *Weight Lifting Exercise Dataset* to assess exercise quality and classify the execution manner using predictive modeling techniques.

The dataset contains motion sensor data collected from participants performing barbell lifts correctly and incorrectly in five different ways. This project’s objective is to build a reproducible machine learning model that accurately predicts the manner of exercise execution.

---

## Data Description
The datasets used in this analysis were obtained from the following sources:

- **Training data:**  
  [https://d396qusza40orc.cloudfront.net/predmachlearn/pml-training.csv](https://d396qusza40orc.cloudfront.net/predmachlearn/pml-training.csv)

- **Testing data:**  
  [https://d396qusza40orc.cloudfront.net/predmachlearn/pml-testing.csv](https://d396qusza40orc.cloudfront.net/predmachlearn/pml-testing.csv)

The training set contains approximately **19,622 observations** and **160 variables**, while the testing set includes **20 cases** for final prediction. The “classe” variable represents the classification labels:  
- A: Correct execution  
- B–E: Variations of incorrect execution

---

## Methodology
### 1. Data Preprocessing
- Removed non-predictive variables such as timestamps, user names, and identifiers.  
- Eliminated variables with near-zero variance or excessive missing values.  
- Ensured consistent data types and proper factor encoding of the target variable (`classe`).  
- Partitioned the training data into **70% training** and **30% validation** subsets to estimate model performance.

### 2. Model Selection and Training
Several algorithms were tested, with a focus on:
- **Random Forest (RF):** chosen for its robustness, resistance to overfitting, and high predictive accuracy on high-dimensional data.  
- **Gradient Boosting Machine (GBM):** used as a comparative model to assess bias–variance tradeoffs.

Cross-validation was implemented using 5-fold resampling through the `caret` package to ensure generalizable results.

### 3. Model Evaluation
Models were evaluated based on:
- Accuracy  
- Kappa statistic  
- Out-of-sample error estimation using the validation dataset

The Random Forest model demonstrated superior accuracy and stability compared to GBM, leading to its selection for final predictions.

---

## Results
The Random Forest model achieved an estimated **out-of-sample accuracy exceeding 99%** on the validation set, indicating strong predictive reliability.  
The model was subsequently applied to the 20 unseen test cases provided by Coursera, producing the final predictions (A–E labels).

---

## Discussion
The results confirm that Random Forest provides exceptional performance for multi-class classification problems involving motion sensor data. The ensemble method effectively captures nonlinear interactions among the features while mitigating overfitting through bootstrap aggregation.  
Despite high accuracy, the model’s interpretability remains limited—a common trade-off with ensemble methods. Future work may include the application of interpretable models or SHAP analysis to better understand feature importance.

---

## Reproducibility
The analysis was performed using **R (version ≥ 4.3)** and the following libraries:
- `caret`  
- `randomForest`  
- `rpart`  
- `ggplot2`  
- `plotly`  
- `shiny` (for interactive visualization)  
- `googleVis`

To reproduce this project:
1. Clone the GitHub repository:  
   ```bash
   git clone https://github.com/haidri671/Weight-Lifting-Project-Analysis.git
