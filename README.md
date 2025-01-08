# Delivery_Duration_Prediction

# Overview
When a consumer places an order on DoorDash, we show the expected time of delivery. It is very important for DoorDash to get this right, as it has a big impact on consumer experience. In this project, we will build a model to predict the estimated time taken for a delivery. This project aims to predict delivery durations using machine learning techniques. The dataset includes various features such as order time, delivery distance, and more. The project involves data preprocessing, visualization, model building, and evaluation.

Concretely, for a given delivery we must predict the total delivery duration seconds , i.e., the time taken from
Start: the time consumer submits the order (created_at) to
End: when the order will be delivered to the consumer (actual_delivery_time). 

### Data Description
The attached file **historical_data.csv** contains a subset of deliveries received at DoorDash in early 2015 in a subset of the cities. Each row in this file corresponds to one unique delivery. We have added noise to the dataset to obfuscate certain business details. Each column corresponds to a feature as explained below. Note all money (dollar) values given in the data are in cents and all time duration values given are in seconds.

The target value to predict here is the total seconds value between 'created_at' and 'actual_delivery_time'.

### Columns in historical_data.csv
#### Time features

- market_id: A city/region in which DoorDash operates, e.g., Los Angeles, given in the data as an id
- created_at: Timestamp in UTC when the order was submitted by the consumer to DoorDash. (Note this timestamp is in UTC, but in case you need it, the actual timezone of the region was US/Pacific)
- actual_delivery_time: Timestamp in UTC when the order was delivered to the consumer
  
#### Store features

- store_id: an id representing the restaurant the order was submitted for
- store_primary_category: cuisine category of the restaurant, e.g., italian, asian
- order_protocol: a store can receive orders from DoorDash through many modes. This field represents an id denoting the protocol
  
#### Order features

- total_items: total number of items in the order
- subtotal: total value of the order submitted (in cents)
- num_distinct_items: number of distinct items included in the order
- min_item_price: price of the item with the least cost in the order (in cents)
- max_item_price: price of the item with the highest cost in the order (in cents)
  
#### Market features

The following features are values at the time of created_at (order submission time):

- total_onshift_dashers: Number of available dashers who are within 10 miles of the store at the time of order creation
- total_busy_dashers: Subset of above total_onshift_dashers who are currently working on an order
- total_outstanding_orders: Number of orders within 10 miles of this order that are currently being processed.

#### Predictions from other models

We have predictions from other models for various stages of delivery process that we can use:

- estimated_order_place_duration: Estimated time for the restaurant to receive the order from DoorDash (in seconds)
- estimated_store_to_consumer_driving_duration: Estimated travel time between store and consumer (in seconds)

### Steps Involved

**1. Data Loading and Exploration:**

- Load the dataset and explore its structure.
- Handle missing values, outliers, and data inconsistencies.

**2. Data Visualization:**

- Visualize distributions, correlations, feature importance of key features using matplotlib and seaborn.
- Analyze relationships between variables to understand the dataset better.

**3. Feature Engineering:**

- Create new features based on existing data (e.g., extracting day, hour from timestamps).
- Normalize or standardize features where necessary.

**4. Model Building:**

  - Train various machine learning models:
    - **Linear Regression:** A simple regression model to establish baseline performance.
    - **Decision Tree Regressor:** Captures non-linear relationships within the data.
    - **Random Forest Regressor:** An ensemble technique improving accuracy by averaging multiple trees.
    - **Gradient Boosting Regressor:** Boosting technique focusing on reducing errors iteratively.
    - **XGBoost Regressor:** An optimized gradient boosting algorithm providing superior performance.
  - Perform hyperparameter tuning for optimal performance.

**5. Model Evaluation:**

- Evaluate models using metrics such as R-squared, Mean Squared Error (MSE), and Mean Absolute Error (MAE).
- Visualize residuals and prediction errors.


### Evaluation Metrics

- **R-squared (R2):** Measures the proportion of variance explained by the model.
- **Mean Squared Error (MSE):** Average squared difference between actual and predicted values.
-** Mean Absolute Error (MAE):** Average absolute difference between actual and predicted values.

### Results

- The Random Forest and XGBoost models showed the highest accuracy based on evaluation metrics.
- Visualizations indicate that certain features like delivery distance and order time significantly affect delivery duration.

### Conclusion
The project demonstrates the effectiveness of machine learning models in predicting delivery durations with high accuracy. Ensemble models like Random Forest and XGBoost outperform simpler models, indicating that capturing non-linear relationships and interactions between features is crucial for improving prediction performance. By leveraging data visualization and feature engineering, the project highlights the importance of understanding the underlying data patterns. The results can aid logistics and delivery companies in optimizing their operations and improving delivery time estimates.
  
### Future Work

- Experiment with additional features to improve model accuracy.
- Implement real-time delivery prediction using the trained model.

## Connect with Me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/sanjay-karnati/)

---


