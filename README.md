FBI Time Series Forecasting
📌 Project Overview
This project focuses on forecasting monthly crime trends using a historical dataset of FBI crime incidents. The dataset includes attributes such as crime type, location (neighborhood, coordinates), and temporal data (year, month, day, hour, minute). The goal is to predict future monthly crime occurrences by crime type using time series modeling, specifically SARIMA. The model achieves 81.57% accuracy with low MAE and RMSE, making it suitable for real-world crime trend forecasting and public safety planning.

🚨 Problem Statement
The objective is to forecast monthly crime trends using historical FBI crime incident data, addressing challenges such as:

Handling missing values, duplicates, and geographical inconsistencies.
Capturing both long-term trends (e.g., overall crime decline) and short-term variations (e.g., seasonal spikes).
Developing a model to provide actionable insights for law enforcement agencies to enhance public safety strategies.

Goals:

Analyze seasonal and long-term crime patterns.
Build and validate a robust time series forecasting model.
Support proactive crime prevention and resource allocation.


📂 Dataset
Filename: Train.xlsx
Features:



Column
Description



TYPE
Type of crime (e.g., Other Theft)


HUNDRED_BLOCK
Street block of crime


NEIGHBOURHOOD
Neighborhood name


X, Y
Spatial coordinates


Latitude, Longitude
Geographic coordinates


HOUR, MINUTE
Time of the crime


YEAR, MONTH, DAY
Date of the crime


Date
Combined datetime field


Key Stats:

Rows: 474,565
Columns: 13
Missing Values:
NEIGHBOURHOOD: 51,491
HOUR, MINUTE: 49,365
HUNDRED_BLOCK: 13


Duplicate Rows: 44,618


🛠 Installation

Clone the Repository:
git clone https://github.com/your-username/fbi-time-series-forecasting.git
cd fbi-time-series-forecasting


Install Dependencies:
pip install -r requirements.txt


Run the Notebook:Open FBI_TIME_SERIES_FORECASTING.ipynb in Jupyter Notebook or JupyterLab:
jupyter notebook FBI_TIME_SERIES_FORECASTING.ipynb



Dependencies (listed in requirements.txt):
numpy
pandas
matplotlib
seaborn
scipy
sklearn
statsmodels


📈 Methodology

Data Preprocessing:

Aggregated data by year, month, and crime type to create a time series.
Handled missing values, duplicates, and geographical outliers.
Converted data into a monthly time series format for analysis.


Exploratory Data Analysis (EDA):

Visualized long-term crime decline and short-term fluctuations.
Confirmed persistent trends and seasonality in the data.


Modeling:

Used SARIMA to capture both trend and seasonality.
Performed stationarity checks (e.g., ADF test) and model tuning.
Split data into training and testing sets for validation.


Evaluation:

Achieved 81.57% accuracy.
Evaluated using metrics like MAE (Mean Absolute Error) and RMSE (Root Mean Squared Error).




📊 Results

The SARIMA model effectively captured long-term trends and seasonal patterns in crime data.
Forecast accuracy: 81.57%.
Low error metrics (MAE and RMSE) indicate reliable predictions.
Visualization of actual vs. forecasted values:
<img src="[images/actual_vs_forecasted.png](https://github.com/krishnaperumalla/FBI-Time-Series-Forecasting/blob/main/README.md)" alt="Actual vs Forecasted Values">


🔍 Conclusion
This project successfully demonstrated the application of time series forecasting to predict monthly crime trends. By addressing data quality issues and leveraging SARIMA, the model provides reliable forecasts that can assist law enforcement in proactive planning and resource allocation. The framework is scalable and can be extended to other crime datasets or forecasting tasks.

🚀 Future Work

Incorporate additional features (e.g., socio-economic factors, weather data) to improve model accuracy.
Explore machine learning models like LSTM or Prophet for comparison.
Deploy the model on a live server for real-time crime trend predictions.


📚 References

FBI Crime Dataset: Train.xlsx
Python Libraries: Pandas, NumPy, Matplotlib, Seaborn, Statsmodels, Scikit-learn
Time Series Forecasting: SARIMA documentation (Statsmodels)


📬 Contact
For questions or contributions, please open an issue or submit a pull request on the GitHub repository.
