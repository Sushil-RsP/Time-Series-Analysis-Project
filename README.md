# Sales Forecasting with Time Series Analysis

## 📊 Project Overview
This project implements time series forecasting for grocery store sales using ARIMA and SARIMAX models. The analysis includes data preprocessing, stationarity testing, model building, and sales prediction for future periods.

## 📁 Dataset
- **File**: `Grocery-Store-Sales-Time-Series-Dataset.csv`
- **Description**: Historical grocery store sales data with monthly records
- **Format**: CSV with Period (date) and Value (sales) columns

## 🔍 Analysis Workflow

### 1. Data Preprocessing
- Loading and parsing date columns
- Handling missing values
- Setting time period as index

### 2. Stationarity Testing
- Visual inspection of the time series
- First-level differencing to achieve stationarity
- ACF and PACF plots for parameter selection

### 3. Model Development

#### ARIMA Model
- **Order**: (1,1,1)
- Manual parameter selection using PACF and ACF
- Train-test split: Last 12 months for testing
- Forecasting 12 months ahead

#### SARIMAX Model (Seasonal ARIMA)
- **Optimal Parameters**: Determined using `auto_arima`
  - Non-seasonal order: (0, 1, 0)
  - Seasonal order: (1, 1, 1, 12)
- Handles seasonality in the data
- Improved prediction accuracy compared to basic ARIMA

### 4. Model Evaluation
- Actual vs Predicted sales comparison
- Error calculation
- Visual comparison plots

## 📦 Dependencies

```python
numpy
pandas
matplotlib
statsmodels
pmdarima
```

## 🚀 Installation

```bash
pip install numpy pandas matplotlib statsmodels pmdarima
```

## 💻 Usage

1. Clone this repository
2. Ensure the dataset is in the same directory
3. Update the file path in the notebook:
   ```python
   data = pd.read_csv(r"your_path\Grocery-Store-Sales-Time-Series-Dataset.csv", skiprows=7)
   ```
4. Run all cells in the Jupyter notebook

## 📈 Key Results

- **ARIMA Model**: Basic forecasting without seasonal components
- **SARIMAX Model**: Improved forecasting with seasonal pattern recognition
- **Forecast Period**: 12 months ahead
- **Visualization**: Comprehensive plots showing historical trends and predictions

## 📊 Visualizations Included

1. Original time series plot
2. Differenced series (stationary)
3. ACF and PACF plots
4. Actual vs Predicted sales (ARIMA)
5. Actual vs Predicted sales (SARIMAX)
6. Historical and forecasted sales

## 🎯 Key Findings

- The sales data exhibits clear seasonality with a 12-month period
- First-level differencing achieves stationarity
- SARIMAX outperforms basic ARIMA due to seasonal component handling
- The model successfully captures seasonal patterns in grocery sales

## 📝 Notes

- The notebook uses the last 12 months of data for testing
- SARIMAX model is recommended for final predictions due to better handling of seasonality
- Forecasts are rounded to whole numbers for practical interpretation

## 🔮 Future Improvements

- Cross-validation for robust model evaluation
- Additional exogenous variables (holidays, promotions)
- Prophet or LSTM models for comparison
- Automated hyperparameter tuning
- Model performance metrics (RMSE, MAE, MAPE)

## 👤 Author

Time Series Analysis Project

## 📄 License

This project is open source and available for educational purposes.
