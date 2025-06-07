Video Game Success Prediction – A Machine Learning Pipeline for Sales Forecasting

This project aims to predict the commercial success of video games using a supervised learning pipeline trained on structured data from the vgsales dataset. The primary objective is to classify or regress global sales performance based on features such as platform, genre, publisher, release year, and regional sales figures.

Data Processing and Feature Engineering

* Dataset: The `vgsales.xls` dataset includes historical sales and metadata for thousands of video game titles.
* Preprocessing: Null values are handled through imputation or row removal (e.g., for missing year or publisher). Categorical variables such as platform, genre, and publisher are encoded using Label Encoding or One-Hot Encoding depending on model compatibility.
* Feature Scaling: Numerical features like `NA_Sales`, `EU_Sales`, `JP_Sales`, and `Other_Sales` are normalized using StandardScaler for algorithms sensitive to scale.

Modeling Pipeline

* Target Variable: Global Sales (either as a regression target in millions of units, or binned into success tiers for classification).
* Algorithms Used: The notebook applies multiple algorithms, including:

  * Linear Regression and Decision Tree Regressor for continuous prediction.
  * Random Forest and Gradient Boosting for both regression and classification tasks.
  * Logistic Regression and SVC for binary or multiclass classification (e.g., predicting if a game will be a hit based on a threshold).
* Hyperparameter tuning via GridSearchCV and k-fold cross-validation ensures generalizability.

Evaluation Metrics

* Regression metrics include Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and R² score.
* Classification metrics include Accuracy, Precision, Recall, F1-score, and ROC-AUC where applicable.
* Feature importance plots are generated for tree-based models to assess the impact of different attributes.

Visualization and Insights

* Correlation heatmaps and pairplots are used to identify multicollinearity and informative features.
* Bar charts and pie plots offer distributional insights by platform, genre, and year.
* PCA (Principal Component Analysis) may be used for dimensionality reduction and visualization of model decision space.

Deployment and Application

* The trained models can be integrated into a lightweight Flask or Streamlit frontend to allow users to input game details and receive sales predictions in real time.
* The solution can aid game developers and publishers in forecasting market performance pre-launch based on historical trends.
