Housing Price Prediction

This project predicts housing prices using Linear Regression and RandomForest on the Housing dataset. It includes data preprocessing, model training, evaluation, and visualizations, implemented in Python using scikit-learn.

Dataset

File: Housing.csv

Description: Contains 545 rows with features (area, bedrooms, bathrooms, stories, mainroad, guestroom, basement, hotwaterheating, airconditioning, parking, prefarea, furnishingstatus) and target (price, in unspecified currency).
How to Run
1.Clone this repository:
git clone https://github.com/yogya111/housing-price-prediction.git
2.Install dependencies:
pip install -r requirements.txt
3.Ensure Housing.csv is in the project directory.
4.Run the notebook:
jupyter notebook Housing_Price_Prediction.ipynb

Methodology

Data Preprocessing:

Removed outliers (prices beyond 3 standard deviations, reducing dataset to ~530 rows).

Log-transformed the target variable (price) to handle skewness.

Mapped categorical variables (yes/no to 1/0) for mainroad, guestroom, basement, hotwaterheating, airconditioning, and prefarea.

One-hot encoded furnishingstatus (dropped first category to avoid multicollinearity).

Scaled numerical features (area, bedrooms, bathrooms, stories, parking) using StandardScaler.

Models:

Linear Regression: Baseline model assuming linear relationships.

RandomForestRegressor: Ensemble model to capture non-linear relationships.

Evaluation:

Metrics: Mean Squared Error (MSE), R-squared (R²), Mean Absolute Error (MAE).

5-fold cross-validation for robust performance estimates.
Visualizations:

Correlation heatmap for numerical features.

Price distribution (before log-transformation).

Actual vs. predicted price plots for both models.

Feature importance for RandomForest.

Results

Linear Regression:

R²: ~0.65 (explains ~65% of variance in log-transformed prices).

MSE: ~0.22 (log scale).

MAE: ~0.33 (log scale).

RandomForest:

R²: ~0.75 (explains ~75% of variance in log-transformed prices).

MSE: ~0.16 (log scale).

MAE: ~0.25 (log scale).

Summary: RandomForest outperforms Linear Regression due to its ability to capture non-linear relationships and interactions between features.

Limitations

Linear Regression assumes linear relationships, limiting its performance on complex patterns.

Limited feature engineering (e.g., no interaction terms like area * bedrooms).

Small dataset (~530 rows after outlier removal) may limit generalizability.

Future Improvements

Experiment with advanced models like XGBoost or Gradient Boosting.

Add feature engineering (e.g., interaction terms, polynomial features).

Tune RandomForest hyperparameters (e.g., n_estimators, max_depth) using GridSearchCV.

Explore additional data cleaning (e.g., handling extreme values in area).




 
