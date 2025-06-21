```markdown
# FBI Time Series Forecasting

## 📌 Project Overview
This project focuses on forecasting **monthly crime trends** using a historical dataset of FBI crime incidents. The dataset includes attributes such as crime type, location (neighborhood, coordinates), and temporal data (year, month, day, hour, minute). The goal is to **predict future monthly crime occurrences by crime type** using time series modeling, specifically SARIMA. The model achieves **81.57% accuracy** with low MAE and RMSE, making it suitable for real-world crime trend forecasting and public safety planning.

---

## 🚨 Problem Statement
The objective is to forecast monthly crime trends using historical FBI crime incident data, addressing challenges such as:
- Handling missing values, duplicates, and geographical inconsistencies.
- Capturing both **long-term trends** (e.g., overall crime decline) and **short-term variations** (e.g., seasonal spikes).
- Developing a model to provide actionable insights for law enforcement agencies to enhance public safety strategies.

**Goals:**
- Analyze seasonal and long-term crime patterns.
- Build and validate a robust time series forecasting model.
- Support proactive crime prevention and resource allocation.

---

## 📂 Dataset
**Filename:** `Train.xlsx`

**Features:**
| Column           | Description                           |
|------------------|---------------------------------------|
| TYPE             | Type of crime (e.g., Other Theft)     |
| HUNDRED_BLOCK    | Street block of crime                 |
| NEIGHBOURHOOD    | Neighborhood name                     |
| X, Y             | Spatial coordinates                   |
| Latitude, Longitude | Geographic coordinates             |
| HOUR, MINUTE     | Time of the crime                     |
| YEAR, MONTH, DAY | Date of the crime                     |
| Date             | Combined datetime field               |

**Key Stats:**
- **Rows**: 474,565
- **Columns**: 13
- **Missing Values**:
  - `NEIGHBOURHOOD`: 51,491
  - `HOUR`, `MINUTE`: 49,365
  - `HUNDRED_BLOCK`: 13
- **Duplicate Rows**: 44,618

---

## 🛠 Installation
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/fbi-time-series-forecasting.git
   cd fbi-time-series-forecasting
   
2. **Install Dependencies**:
   ```bash
   pip install numpy pandas matplotlib seaborn scipy sklearn statsmodels
   

3. **Download Dataset**:
   - Place `Train.xlsx` in the project directory.

---

## 📈 Methodology
1. **Data Preprocessing**:
   - Aggregated data by year, month, and crime type to create a time series dataset.
   - Handled missing values, duplicates, and geographical outliers to ensure data quality.

2. **Exploratory Data Analysis (EDA)**:
   - Visualized time series data to identify a long-term decline in crime rates and short-term seasonal fluctuations.
   - Confirmed consistent patterns in recent data, validating the dataset's suitability for forecasting.

3. **Model Selection**:
   - Used **SARIMA** to capture both trend and seasonality in crime data.
   - Performed stationarity checks (e.g., ADF test) and analyzed ACF/PACF plots to determine model parameters.

4. **Model Training and Evaluation**:
   - Split data into training and test sets.
   - Trained SARIMA model and evaluated performance using:
     - **Accuracy**: 81.57%
     - **Mean Absolute Error (MAE)** and **Root Mean Squared Error (RMSE)** for forecast accuracy.

5. **Visualization**:
   - Plotted actual vs. forecasted values to assess model performance.

   ![Actual vs Forecasted Values](path/to/your/plot.png)

---

## 📊 Results
- The SARIMA model effectively captured long-term trends and seasonal patterns in the crime data.
- Achieved **81.57% accuracy** with low MAE and RMSE, indicating reliable predictions.
- The model is ready for deployment to support real-time crime forecasting.

---

## 🚀 Usage
1. **Run the Notebook**:
   ```bash
   jupyter notebook FBI_TIME_SERIES_FORECASTING.ipynb
   

2. **Key Steps in Notebook**:
   - Load and preprocess the dataset.
   - Perform EDA and visualize trends.
   - Train the SARIMA model and generate forecasts.
   - Evaluate and visualize results.

3. **Example Output**:
   - Forecasted monthly crime counts by crime type.
   - Visual comparison of actual vs. forecasted values (as shown above).
  ![image](https://github.com/user-attachments/assets/4a047d02-63ca-4375-be2b-49fd87edd8f8)

---

## 🔍 Conclusion
This project successfully demonstrates the application of time series forecasting to predict FBI crime trends. By addressing data quality issues and leveraging SARIMA, the model provides reliable predictions for monthly crime occurrences. The insights generated can aid law enforcement in:
- Proactive crime prevention.
- Optimized resource allocation.
- Strategic planning for public safety.

The framework is scalable and can be extended to other time series forecasting tasks in the criminal justice domain.

---

## 📚 Dependencies
- Python 3.x
- Libraries: `numpy`, `pandas`, `matplotlib`, `seaborn`, `scipy`, `sklearn`, `statsmodels`

---

## 📬 Contact
For questions or contributions, please open an issue or contact [your-email@example.com](mailto:your-email@example.com).

---
