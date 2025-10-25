# In-Depth EDA and Predictive Modeling on Diabetes Dataset
Project Overview
This project performs an in-depth Exploratory Data Analysis (EDA) and builds predictive models to understand the factors influencing diabetes risk and predict diabetes diagnosis based on a comprehensive dataset.

**Dataset**
The analysis is based on the diabetes_dataset.csv file. This dataset contains various health and demographic attributes for a large number of individuals and includes a target variable indicating whether an individual was diagnosed with diabetes.

**Key features in the dataset include:**

Demographic information (Age, Gender, Ethnicity, Education Level, Income Level, Employment Status)
Lifestyle factors (Smoking Status, Alcohol Consumption, Physical Activity, Diet Score, Sleep Hours, Screen Time)
Medical history (Family History of Diabetes, Hypertension History, Cardiovascular History)
Biometric measurements (BMI, Waist-to-Hip Ratio, Blood Pressure, Heart Rate)
Blood test results (Cholesterol Levels - Total, HDL, LDL, Triglycerides, Glucose - Fasting and Postprandial, Insulin Level, HbA1c)
Diabetes-specific metrics (Diabetes Risk Score, Diabetes Stage, Diagnosed Diabetes - Target Variable)

**Methodology**
The project follows a structured approach:

**Data Loading and Preprocessing:**
Loading the dataset into a pandas DataFrame.
Handling missing values through inspection and median imputation for numerical features.
Identifying and addressing inconsistencies, such as biologically implausible zero values in certain columns.
Checking for and noting duplicate records.
**Basic Analysis:**
Displaying descriptive statistics of the dataset.
Analyzing the distribution of the target variable (diagnosed_diabetes).
Visualizing feature distributions using histograms and comparing mean vs. median for skewed features.
**Intermediate Analysis:**
Calculating and visualizing the correlation matrix to understand relationships between numerical features and the target variable.
Exploring feature distributions by outcome using box plots and KDE plots.
Analyzing grouped statistics to compare mean feature values between diabetic and non-diabetic groups.
Visualizing pairwise feature relationships using pair plots.
**Advanced Analysis & Predictive Modeling:**
Applying Principal Component Analysis (PCA) for dimensionality reduction and visualization.
Training and evaluating predictive models, including Logistic Regression and Random Forest classifiers.
Performing hyperparameter tuning on the Random Forest model using RandomizedSearchCV on a sampled subset of the data.
Evaluating the performance of the tuned Random Forest model on the full test set.
Conclusion and Interpretation: Summarizing key findings from EDA and predictive modeling, discussing model performance, and providing recommendations.
**Key Findings**
Glucose levels (both fasting and postprandial) are the strongest predictors of diabetes risk, showing significantly higher values in diabetic individuals.
BMI and Age are also important factors positively correlated with diabetes diagnosis.
Diabetes Risk Score is highly correlated with the diagnosed diabetes outcome.
Other features like Waist-to-Hip Ratio and Systolic Blood Pressure show moderate correlations.
Features such as Alcohol Consumption, Diet Score, and Screen Time show weak individual correlations but may contribute in combination.
PCA visualization indicated some separation between the two outcome classes in the feature space, though with considerable overlap.

# Predictive Modeling Results
**Three models were trained and evaluated:**

Logistic Regression: Achieved an accuracy of 0.83 and an ROC AUC of 0.9115 on the test set, providing a solid baseline.
Untuned Random Forest: Showed superior performance with an accuracy of 0.94 and an ROC AUC of 0.9806 on the test set, demonstrating its ability to capture complex patterns.
Tuned Random Forest (Evaluated on Full Test Set): After tuning on a sampled subset, the model achieved an accuracy of 0.8548 and an ROC AUC of 0.9218 on the full test set. While better than Logistic Regression, the performance was slightly lower than the untuned model evaluated directly on the full test set, suggesting potential benefits of tuning on the full training set if resources allow.
The Random Forest model consistently outperformed Logistic Regression, highlighting the non-linear relationships present in the data.

# **Conclusion and Recommendations**
The analysis confirms that glucose levels, BMI, and age are significant indicators of diabetes risk. The Random Forest model demonstrated strong predictive capabilities for diabetes diagnosis based on the provided features.

# Recommendations:

The tuned Random Forest model is a promising candidate for predicting diabetes risk.
For further improvement, consider hyperparameter tuning on the entire training set using cross-validation for more robust optimization.
Exploring techniques to address class imbalance could further enhance model performance, particularly for the minority class.
In a real-world application, balance model performance with interpretability needs.
**How to Run the Notebook**
Open the notebook in Google Colab.
Ensure the diabetes_dataset.csv file is accessible in the /content/ directory (as used in the notebook).
Run each code cell sequentially.
**Acknowledgments
Grateful to my co-learners and collaborators: Chirag Jhumkhawala, Vinay Sutar, Pranav Jaipurkar, Sandhya Hinduja, Shivani Tripathi**
