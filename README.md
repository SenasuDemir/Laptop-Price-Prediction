# Laptop Price Prediction using Machine Learning

This project aims to predict laptop prices based on various features and specifications using **regression** machine learning algorithms. The dataset contains information about different laptop models, their configurations, and corresponding prices.

## Objective

The primary goal of this project is to leverage machine learning techniques, specifically **regression models**, to predict laptop prices based on their specifications.

## Dataset Overview

The dataset contains specifications and pricing information for various laptops. Below is a detailed explanation of each column:

| **Column**         | **Description**                                                                                      |
|--------------------|------------------------------------------------------------------------------------------------------|
| **Company**        | The brand or manufacturer of the laptop (e.g., Apple, HP).                                          |
| **TypeName**       | The category or type of the laptop (e.g., Ultrabook, Notebook).                                      |
| **Inches**         | The screen size of the laptop, measured diagonally in inches.                                       |
| **ScreenResolution**| The resolution of the screen, which may include additional details like panel type (e.g., IPS).     |
| **Cpu**            | The processor specifications, including brand, model, and clock speed (e.g., Intel Core i5 2.3GHz). |
| **Ram**            | The amount of RAM (Random Access Memory) available in the laptop, typically measured in GB.         |
| **Memory**         | The storage capacity and type of the laptop (e.g., 128GB SSD, 128GB Flash Storage).                 |
| **Gpu**            | The graphics processing unit details, specifying integrated or dedicated GPU models.                |
| **OpSys**          | The operating system pre-installed on the laptop (e.g., macOS, No OS).                              |
| **Weight**         | The weight of the laptop, specified in kilograms (kg).                                              |
| **Price**          | The price of the laptop, in the specified currency (e.g., INR or USD).                              |

## Data Exploration

We analyzed the correlations between laptop features and prices. Significant features influencing prices were identified, such as:

- **Weight**
- **CPU Speed (GHz)**
- **Weight per Inch**

## Feature Engineering

To enhance model performance, we created new features such as:

- **TouchScreen**: Whether the laptop has a touchscreen display.
- **IPS Display**: Whether the laptop has an IPS panel.
- **IntelCoreGpu**: Indicates whether the GPU is part of the Intel Core series.
- **Cpu_Speed_GHz**: The CPU speed, converted to GHz.
- **Screen_Width**: The width of the laptop screen in inches.
- **Screen_Height**: The height of the laptop screen in inches.
- **Aspect_Ratio**: The aspect ratio of the laptop screen (width/height).
- **Screen_Area**: The total screen area in square inches(width*height).
- **Storage_Size_GB**: The storage size of the laptop, measured in GB.
- **Storage_Type**: The type of storage (e.g., SSD, HDD, Flash).
- **High_Quality_Display**: Whether the laptop screen is of high quality (e.g., Full HD, 4K).
- **Weight_per_Inch**: The weight of the laptop relative to the screen size (kg/inch).

## Preprocessing

The data was preprocessed by:

- Handling missing values.
- Converting data types.
- Cleaning the dataset to ensure compatibility with machine learning algorithms.


## Model Evaluation

We evaluated the performance of each model using the following metrics:

- **R-Squared** (R²)
- **Root Mean Squared Error** (RMSE)
- **Mean Absolute Error** (MAE)

Here are the results from the different models:

| Model                | R²        | RMSE            | MAE             |
|----------------------|-----------|-----------------|-----------------|
| XGBoost Regressor    | 0.869459  | 11242.15        | 7730.76         |
| Random Forest Regressor | 0.865709 | 11402.48        | 7761.71         |
| Extra Trees          | 0.844982  | 12250.85        | 8087.75         |
| Gradient Boosting    | 0.816974  | 13311.65        | 9410.73         |
| Decision Tree Regressor | 0.780571 | 14575.46        | 9950.33         |
| K-Neighbors Regressor | 0.753648 | 15443.78        | 11219.89        |
| Lasso Regression     | 0.743190  | 15768.19        | 11202.65        |
| Linear Regression    | 0.742711  | 15782.87        | 11200.23        |
| Ridge Regression     | 0.740003  | 15865.73        | 11468.93        |
| ElasticNet           | 0.708903  | 16787.84        | 13109.03        |

## Hyperparameter Tuning

We optimized the **Random Forest Regressor** using **GridSearchCV** to improve performance, yielding slightly better results.

## Model Interpretation

The **XGBoost Regressor** achieved the best performance with an **R² of 0.869**, **RMSE of 11242**, and **MAE of 7730**. This indicates that the model can predict laptop prices with **86.9% accuracy**.

Key insights from the feature importance plot generated by **XGBoost**:

- **Weight**
- **CPU Speed (GHz)**
- **Weight per Inch**

These features were found to be the most influential in predicting laptop prices, highlighting the importance of both physical attributes and processing power.

## Conclusion

This project demonstrates how **regression machine learning models** can predict laptop prices with high accuracy based on various specifications. The **XGBoost Regressor** outperformed other models, offering the best predictive capability for this dataset.
