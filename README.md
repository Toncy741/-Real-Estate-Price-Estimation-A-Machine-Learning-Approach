# -Real-Estate-Price-Estimation-A-Machine-Learning-Approach


...* Data Ingestion and Initial Cleaning

I start the notebook by loading the New York City property sales CSV into a pandas DataFrame and immediately filtering out any non-residential transactions or sales before 2003. I standardize the column names to snake_case for consistency, convert the sale date column into a datetime dtype, and then address missing or implausible values—dropping rows where sale price or living area is zero or null, and filling or excluding other gaps as needed.

...*Exploratory Data Analysis

With a cleaned dataset in hand, I dive into exploratory analysis. I plot the distribution of sale prices and notice a strong right skew, so I examine boxplots and histograms of price by borough, neighborhood, and building class. I also chart year-over-year trends to spot market cycles, which helps me identify outliers and understand which variables show the greatest variation.

...*Feature Engineering

Next, I transform and augment my data to improve model performance. I apply a log transformation to both sale price and living area to stabilize their variances. I create a new “building_age” feature by subtracting the year built from the sale year, and compute “price_per_sqft” to capture unit efficiency. To allow tree-based models to learn location and temporal effects, I one-hot encode categorical fields such as borough, building class, and sale year.

...*Train/Test Split and Baseline Modeling

I split the processed dataset into an 80/20 train/test split. As a baseline, I fit a simple linear regression model on the training set and evaluate its root-mean-square error (RMSE) and R² on the hold-out data, confirming that it struggles to capture the complexities of the market.

...*Advanced Model Training

After establishing the baseline, I train two more powerful models: a random forest regressor and a gradient boosting regressor. I use cross-validation on the training set to tune key hyperparameters—such as the number of estimators, maximum tree depth, and learning rate—seeking the best balance of bias and variance.

...*Model Evaluation and Comparison

I evaluate all three models on the test set, comparing their RMSE and R² scores to see which offers the most accurate predictions. I also generate scatter plots of predicted versus actual prices and extract feature importances from the ensemble models to understand which engineered variables most heavily influence the estimates.


...*model ready for deployment.

Finally, I assemble a concise summary of my findings. I present a table of each model’s performance metrics, bar charts of top feature importances, and residual plots to diagnose any systematic errors. These final cells give anyone reviewing the notebook a clear, reproducible path from raw data to a tuned gradient boosting 







