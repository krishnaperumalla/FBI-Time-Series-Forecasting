FBI Time Series Forecasting
Project Overview
This project focuses on forecasting monthly crime trends using a historical dataset of crime incidents provided by the FBI. The dataset includes detailed records of crime incidents with attributes such as crime type, location (neighborhood, coordinates), and temporal information (year, month, day, hour, minute). The primary goal is to predict future monthly crime occurrences by crime type, leveraging time series analysis to provide actionable insights for public safety strategies and crime prevention.
The project employs data preprocessing, exploratory data analysis (EDA), and the SARIMA model to capture long-term trends and short-term fluctuations in crime data. The final model achieves a high accuracy of 81.57% with low forecast error metrics (MAE and RMSE), demonstrating its effectiveness for real-world applications.
Table of Contents

Project Overview
Problem Statement
Dataset
Installation
Usage
Methodology
Results
Directory Structure
Contributing
License
Contact
Acknowledgments

Problem Statement
The objective is to forecast monthly crime trends using a historical dataset of crime incidents. The dataset contains challenges such as missing values, duplicate entries, and geographical inconsistencies. The project aims to:

Analyze long-term crime trends and short-term variations.
Develop a robust time series forecasting model (SARIMA) to predict future crime occurrences.
Provide actionable insights for law enforcement agencies to enhance public safety strategies.

Dataset
The dataset (Train.xlsx) contains crime incident records with the following columns:

TYPE: Type of crime (e.g., Other Theft).
HUNDRED_BLOCK: Street block where the crime occurred.
NEIGHBOURHOOD: Neighborhood of the crime.
X, Y: Spatial coordinates.
Latitude, Longitude: Geographic coordinates.
HOUR, MINUTE: Time of the crime.
YEAR, MONTH, DAY: Date of the crime.
Date: Combined datetime field.

Key Statistics:

Rows: 474,565
Columns: 13
Missing Values: Notable in NEIGHBOURHOOD (51,491), HOUR (49,365), MINUTE (49,365), and HUNDRED_BLOCK (13).
Duplicates: 44,618 rows.

The data was aggregated by year, month, and crime type to create a time series for forecasting.
Installation
To run this project locally, follow these steps:

Clone the Repository:
git clone https://github.com/your-username/fbi-time-series-forecasting.git
cd fbi-time-series-forecasting


Set Up a Virtual Environment (recommended):
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate


Install Dependencies:Install the required Python libraries using the provided requirements.txt:
pip install -r requirements.txt

requirements.txt:
numpy
pandas
matplotlib
seaborn
scipy
scikit-learn
statsmodels


Download the Dataset:Place the Train.xlsx dataset in the project root directory or update the file path in the notebook (FBI_TIME_SERIES_FORECASTING.ipynb).

Run the Jupyter Notebook:
jupyter notebook FBI_TIME_SERIES_FORECASTING.ipynb



Usage

Open the FBI_TIME_SERIES_FORECASTING.ipynb notebook in Jupyter.
Ensure the dataset (Train.xlsx) is in the correct directory.
Run the notebook cells sequentially to:
Load and preprocess the dataset.
Perform exploratory data analysis (EDA).
Train the SARIMA model.
Generate forecasts and evaluate model performance.


View the visualizations (e.g., actual vs. forecasted crime counts) and performance metrics (MAE, RMSE, MAPE).

The notebook is self-contained and includes comments for each step. Modify parameters (e.g., SARIMA order, forecast horizon) as needed for experimentation.
Methodology

Data Preprocessing:

Handled missing values in NEIGHBOURHOOD, HOUR, and MINUTE columns.
Removed or addressed 44,618 duplicate rows.
Corrected geographical outliers in X, Y, Latitude, and Longitude.
Aggregated data by year, month, and crime type to create a monthly time series.


Exploratory Data Analysis (EDA):

Visualized crime trends over time, revealing a long-term decline with short-term fluctuations.
Analyzed seasonality and stationarity using ACF/PACF plots and the Augmented Dickey-Fuller (ADF) test.
Confirmed persistent patterns in newer data, validating the dataset's forecasting potential.


Modeling:

Selected the SARIMA model for its ability to capture both trend and seasonality.
Split data into training and test sets.
Trained the SARIMA model and tuned parameters for optimal performance.
Generated forecasts for future months.


Evaluation:

Evaluated model performance using:
Mean Absolute Error (MAE): Measures average forecast error.
Root Mean Squared Error (RMSE): Penalizes larger errors.
Mean Absolute Percentage Error (MAPE): Provides error as a percentage.


Achieved an accuracy of 81.57% on the test set.



Results

Model Performance:

Accuracy: 81.57%
MAE: Low, indicating accurate predictions.
RMSE: Low, showing robustness against larger errors.
MAPE: Indicates reliable percentage-based error.


Key Insights:

Crime rates exhibit a long-term decline with short-term fluctuations.
The SARIMA model effectively captures both trends and seasonal patterns.
Forecasts can guide law enforcement in resource allocation and crime prevention strategies.


Visualization:

Plots of actual vs. forecasted crime counts demonstrate close alignment, as shown in the notebook.



Directory Structure
fbi-time-series-forecasting/
├── FBI_TIME_SERIES_FORECASTING.ipynb  # Main Jupyter notebook
├── Train.xlsx                         # Dataset (not included in repo; add manually)
├── requirements.txt                   # Python dependencies
├── README.md                          # This file
└── outputs/                           # Directory for generated plots and results (optional)

Contributing
Contributions are welcome! To contribute:

Fork the repository.
Create a new branch (git checkout -b feature-branch).
Make your changes and commit (git commit -m "Add feature").
Push to the branch (git push origin feature-branch).
Open a pull request with a detailed description of your changes.

Please ensure your code follows the project's coding style and includes appropriate documentation.
License
This project is licensed under the MIT License. See the LICENSE file for details.
Contact
For questions or feedback, please contact:

Your Name: your.email@example.com
GitHub: your-username

Acknowledgments

The FBI for providing the crime dataset.
The open-source community for libraries like pandas, statsmodels, and matplotlib.
Contributors and reviewers who provided valuable feedback.

