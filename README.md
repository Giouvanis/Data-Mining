# Data-Mining
Heart Disease Prediction using SVM and Random Forest
This repository contains a machine learning project focused on predicting the presence or absence of heart disease using clinical patient attributes. Early detection and accurate prediction of cardiovascular risks can significantly aid timely medical intervention and patient management.  
The project implements, tunes, and compares two robust classification algorithms: Support Vector Machines (SVM) and Random Forest (RF).  

📂 Dataset Overview
The dataset contains 918 records with 11 clinical features and a binary target variable (HeartDisease):  

Features:
Age: Age of the individual in years.  
Sex: Gender of the individual (Male/Female).  
ChestPainType: Type of chest pain experienced.  
RestingBP: Resting blood pressure (in mm Hg).  
Cholesterol: Serum cholesterol level (in mg/dl).  
FastingBS: Fasting blood sugar (> 120 mg/dl: 1, <= 120 mg/dl: 0).  
RestingECG: Resting electrocardiographic results.  
MaxHR: Maximum heart rate achieved.  
ExerciseAngina: Exercise-induced angina (Yes/No).  
Oldpeak: ST depression induced by exercise relative to rest.  
ST_Slope: The slope of the peak exercise ST segment.  
HeartDisease (Target): Presence of heart disease (0: No, 1: Yes).  

🛠️ Workflow & Methodology
Data Cleaning & Transformation:

Verified that the dataset has no missing values.  
Converted categorical variables into dummy variables using One-Hot Encoding (pd.get_dummies).  
Data Partitioning: Split the data into 75% training and 25% testing sets. A fixed seed (random_state=42) was utilized to guarantee reproducibility.  
Feature Standardization: Standardized independent variables using StandardScaler to ensure a mean of 0 and a standard deviation of 1.  
Hyperparameter Optimization: Conducted grid search with 5-fold cross-validation (GridSearchCV) to locate the optimal parameters for both classifiers.  

⚙️ Hyperparameter Tuning Results
Support Vector Classifier (SVC)
Parameter Grid: Evaluated Regularization Parameter (C) and Kernel types (Linear, Polynomial, RBF, Sigmoid).  
Optimal Parameters: {'C': 0.1, 'kernel': 'linear'}.  
Best CV Score: 0.8648.  
Random Forest Classifier
Parameter Grid: Evaluated number of trees (n_estimators) and maximum feature splits (max_features).  
Optimal Parameters: {'max_features': 'sqrt', 'n_estimators': 150}.  
Best CV Score: 0.8633.  

📊 Evaluation & Model Comparison
After training the optimized models on the full training set, we evaluated their classification performance on the unseen test partition:  

Model	Test Accuracy
Random Forest	
87.39%

Support Vector Machine	
85.65%

Visualizing Decision Boundaries (Age vs. RestingBP)
We generated and compared the decision boundaries of both classifiers based on the standardized features Age and RestingBP:  

SVM Boundary: Yields a clean, linear boundary due to the selected linear kernel.  

Random Forest Boundary: Demonstrates more complex, non-linear axis-aligned splits representing the ensemble of decision trees.  

(Insert your saved plots here to make your repository stand out!)
<img width="692" height="535" alt="image" src="https://github.com/user-attachments/assets/4b82b086-c0fd-4a16-b999-cacb3cc0ac6f" />

<img width="709" height="553" alt="image" src="https://github.com/user-attachments/assets/055c9c9f-d916-476b-af3f-65f841a50b8b" />

🧠 Clinical Context & Insights
The relationship between Cholesterol and Blood Pressure plays a pivotal role in predicting cardiovascular risk:  

Atherosclerosis: High levels of LDL cholesterol promote plaque buildup inside the arterial walls, narrowing the pathway for blood flow. This structural restriction increases arterial resistance, forcing the heart to pump harder and directly raising resting blood pressure.  

Endothelial Dysfunction: Elevated cholesterol levels damage the endothelium (inner lining of blood vessels), reducing their capacity to dilate dynamically. This structural stiffness, paired with systemic lipid-induced inflammation, further compounds hypertensive risk.  

Both features serve as crucial clinical indicators that allow machine learning models to map patient-specific cardiovascular vulnerability.  
