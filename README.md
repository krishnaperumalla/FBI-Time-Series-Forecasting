# FBI Time Series Forecasting
[![Ask DeepWiki](https://devin.ai/assets/askdeepwiki.png)](https://deepwiki.com/krishnaperumalla/FBI-Time-Series-Forecasting)

## 📌 Project Overview
This project focuses on analyzing and forecasting monthly crime trends using a historical dataset of FBI crime incidents. The dataset includes attributes such as crime type, location, and temporal data spanning from 1999 to 2011. The primary objective is to predict future monthly crime occurrences by leveraging time series modeling, specifically SARIMA (Seasonal AutoRegressive Integrated Moving Average).

The final model successfully captures both long-term trends and seasonality in crime rates, achieving an accuracy of **81.57%** with low Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE). The insights from this forecast can be used by law enforcement agencies for proactive crime prevention, strategic planning, and resource allocation.

## 🚨 Problem Statement
The goal is to develop a robust forecasting model that predicts monthly crime trends using historical FBI crime incident data. This involves addressing several challenges:
*   Handling data quality issues such as missing values, duplicate entries, and geographical inconsistencies.
*   Capturing complex temporal patterns, including long-term declines in crime and short-term seasonal variations.
*   Building a model that provides actionable insights to help law enforcement enhance public safety strategies.

## 📂 Dataset
The analysis is based on a single dataset containing crime incident records.

*   **Filename:** `Train.xlsx`
*   **Rows:** 474,565
*   **Columns:** 13
*   **Missing Values:** Primarily in `NEIGHBOURHOOD` (51,491) and `HOUR`/`MINUTE` (49,365).
*   **Duplicate Rows:** 44,618

### Features
| Column        | Description                                  |
|---------------|----------------------------------------------|
| `TYPE`        | Type of crime (e.g., Other Theft)            |
| `HUNDRED_BLOCK` | Street block where the crime occurred        |
| `NEIGHBOURHOOD` | Neighborhood name of the crime location      |
| `X`, `Y`        | Spatial coordinates (projected)              |
| `Latitude`    | Geographic latitude coordinate               |
| `Longitude`   | Geographic longitude coordinate              |
| `HOUR`, `MINUTE`| Time of the crime (24-hour format)         |
| `YEAR`, `MONTH`, `DAY` | Date of the crime                     |
| `Date`        | Combined timestamp field for the incident    |


## 🛠️ Setup and Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/krishnaperumalla/fbi-time-series-forecasting.git
    cd fbi-time-series-forecasting
    ```

2.  **Install the required dependencies:**
    ```bash
    pip install numpy pandas matplotlib seaborn scipy statsmodels scikit-learn xgboost
    ```

3.  **Run the Jupyter Notebook:**
    Launch Jupyter Notebook or JupyterLab and open `FBI_TIME_SERIES_FORECASTING.ipynb`.
    ```bash
    jupyter notebook FBI_TIME_SERIES_FORECASTING.ipynb
    ```

## 📈 Methodology

The project followed a structured approach to build the forecasting model:

1.  **Data Preprocessing:**
    *   Loaded the dataset and handled initial data quality issues.
    *   Filled missing `HOUR` and `MINUTE` values using the mean. Dropped rows with other critical missing data.
    *   Treated geographical outliers using the Interquartile Range (IQR) method.
    *   Aggregated the data into a monthly time series by counting the number of crime incidents per month.

2.  **Exploratory Data Analysis (EDA):**
    *   Visualized crime frequency by type, hour of the day, and neighborhood to identify key patterns.
    *   Plotted the time series data to observe long-term trends and seasonality.

3.  **Time Series Analysis:**
    *   Checked for stationarity using the Augmented Dickey-Fuller (ADF) test. The original series was found to be non-stationary.
    *   Applied differencing to make the time series stationary, a necessary step for SARIMA modeling.
    *   Analyzed Autocorrelation (ACF) and Partial Autocorrelation (PACF) plots to determine the optimal parameters for the model.

4.  **Modeling and Evaluation:**
    *   Split the data into 80% for training and 20% for testing.
    *   Implemented a **SARIMA(1, 1, 2)(0, 1, 1, 12)** model to capture both non-seasonal and seasonal (yearly) patterns.
    *   Evaluated the model's performance on the test set using MAE, RMSE, and Mean Absolute Percentage Error (MAPE).

## 📊 Results

The SARIMA model demonstrated strong predictive performance on the test data.

*   **Accuracy:** **81.57%**
*   **Mean Absolute Error (MAE):** 19.13
*   **Root Mean Squared Error (RMSE):** 23.39

The low error metrics indicate that the model's forecasts are reliable and closely follow the actual crime trends. The visualization below compares the actual crime counts with the values forecasted by the model.

![Actual vs. Forecasted Values](https://raw.githubusercontent.com/krishnaperumalla/FBI-Time-Series-Forecasting/main/Output_graph)

## 🔍 Conclusion
This project successfully demonstrates the power of time series forecasting for crime analysis. By systematically cleaning the data, identifying temporal patterns, and applying a SARIMA model, we developed a reliable tool for predicting monthly crime trends. The resulting forecasts, with an accuracy of over 81%, can serve as a valuable resource for law enforcement agencies, enabling data-driven resource allocation and proactive crime prevention strategies. The established framework is scalable and can be adapted for other crime datasets or forecasting tasks.

## 🚀 Future Work
*   **Enhance Feature Engineering:** Incorporate external data such as socio-economic factors, weather data, or public events to improve model accuracy.
*   **Explore Alternative Models:** Compare the SARIMA model's performance with other advanced forecasting techniques like LSTM (Long Short-Term Memory) networks or Prophet.
*   **Deployment:** Package the final model using `pickle` and deploy it as a web service or dashboard for real-time predictions and user interaction.
