🚚 Air Pressure System Failure Prediction (Scania Trucks)
📌 Project Overview

  Modern heavy-duty trucks are equipped with hundreds of sensors that continuously monitor system health.
  This project focuses on predicting Air Pressure System (APS) failures in Scania trucks using machine learning, enabling early fault detection and preventive maintenance.

  The task is formulated as a binary classification problem on highly imbalanced, high-dimensional industrial sensor data.

🎯 Objective

  Predict whether a truck’s air pressure system will fail (pos) or not (neg)
  
  Handle real-world challenges such as missing values, high dimensionality, and class imbalance
  
  Compare classical and ensemble ML models to identify the most effective approach

📊 Dataset

  Source: Scania APS Failure Dataset (UCI Machine Learning Repository)
  
  Instances: ~60,000
  
  Features: 170+ sensor readings
  
  Target: class
  
  0 → No failure (neg)
  
  1 → APS failure (pos)

Challenges:

  Large number of missing values ("na")
  
  Severe class imbalance (~98% non-failure, ~2% failure)

🧠 Methodology
  1. Data Preprocessing
  
  Replaced "na" values with NaN
  
  Converted all sensor features from object to numeric types
  
  Imputed missing values using median (robust to skewed sensor distributions)
  
  Encoded target labels (neg → 0, pos → 1)
  
  Applied StandardScaler for feature normalization
  
  2. Model Training
  
  The following models were trained and evaluated:
  
  Logistic Regression (baseline, interpretable)
  
  Random Forest Classifier (nonlinear ensemble)
  
  Gradient Boosting Classifier (boosted ensemble)
  
  Class imbalance was handled using class weighting.
  
  3. Evaluation Metrics
  
  Given the imbalance, model performance was assessed using:
  
  Accuracy
  
  Precision, Recall, and F1-score (especially for failure class)
  
  Confusion Matrix

📈 Results
  Model	Accuracy	Recall (Failure)	F1-score (Failure)
  Logistic Regression	97.4%	0.81	0.51
  Random Forest	98.9%	0.46	0.59
  Gradient Boosting	99.1%	0.53	0.66

  Gradient Boosting achieved the best overall balance between accuracy and failure detection performance.

🔍 Key Insights

  Ensemble models significantly outperform linear baselines on complex sensor interactions
  
  Gradient Boosting provides the best trade-off between precision and recall for failure detection
  
  Feature importance analysis highlights key sensor signals correlated with APS failures

🛠️ Tech Stack

  Language: Python
  
  Libraries:
  
  pandas, numpy
  
  scikit-learn
  
  matplotlib, seaborn
