# 📈 Cryptocurrency Volatility Prediction

A complete machine learning project for predicting short-term cryptocurrency volatility using historical market data. This project demonstrates end-to-end ML pipeline development, from data preprocessing to model deployment.

## 🎯 Project Overview

**Objective:** Predict 7-day rolling volatility for cryptocurrencies using Random Forest Regressor

**Target Variable:** 7-day rolling volatility (standard deviation of log returns)

**Dataset:** Historical cryptocurrency market data with OHLC prices, volume, and market capitalization

## 🏗️ Project Structure

```
crypto-volatility-prediction/
│
├── data/
│   ├── raw/                    # Raw dataset storage
│   └── processed/              # Processed and feature-engineered data
│
├── notebooks/
│   ├── 01_eda.ipynb           # Exploratory Data Analysis
│   ├── 02_feature_engineering.ipynb
│   └── 03_model_training.ipynb
│
├── src/
│   ├── preprocessing.py        # Data preprocessing module
│   ├── feature_engineering.py  # Feature creation module
│   ├── train_model.py         # Model training module
│   └── evaluate_model.py      # Model evaluation module
│
├── model/
│   ├── volatility_model.pkl   # Trained model
│   └── test_data.pkl          # Test dataset
│
├── reports/
│   ├── HLD.md                 # High Level Design
│   ├── LLD.md                 # Low Level Design
│   ├── Pipeline_Architecture.md
│   ├── EDA_Report.md
│   └── Final_Report.md
│
├── app.py                     # Streamlit deployment app
├── requirements.txt           # Python dependencies
└── README.md                  # Project documentation
```

## 🚀 Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/crypto-volatility-prediction.git
cd crypto-volatility-prediction
```

### 2. Create Virtual Environment

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Prepare Data

Place your `dataset.csv` file in the `data/raw/` directory with the following columns:
- date
- crypto_name
- open
- high
- low
- close
- volume
- marketCap

### 5. Run the Pipeline

```bash
# Step 1: Data Preprocessing
python src/preprocessing.py

# Step 2: Feature Engineering
python src/feature_engineering.py

# Step 3: Model Training
python src/train_model.py

# Step 4: Model Evaluation
python src/evaluate_model.py
```

### 6. Launch Streamlit App

```bash
streamlit run app.py
```

The app will open in your browser at `http://localhost:8501`

## 📊 Features

### Data Preprocessing
- Missing value handling
- Data consistency checks
- Outlier removal
- Time-based sorting

### Feature Engineering

**Technical Indicators:**
- Log returns
- Rolling volatility (7-day, 14-day)
- Moving averages (MA7, MA14, MA30)
- Bollinger Band width
- Average True Range (ATR)
- Liquidity ratio (volume/marketCap)
- Momentum indicators

### Model Development
- **Algorithm:** Random Forest Regressor
- **Train-Test Split:** Time-based 80/20 split
- **Hyperparameter Tuning:** GridSearchCV with 3-fold cross-validation
- **Features:** 14 engineered features

### Model Evaluation Metrics
- **RMSE** (Root Mean Squared Error)
- **MAE** (Mean Absolute Error)
- **R² Score** (Coefficient of Determination)
- **MAPE** (Mean Absolute Percentage Error)

### Deployment
- Interactive Streamlit web application
- CSV file upload functionality
- Cryptocurrency selection
- Real-time volatility predictions
- Visualization and download options

## 📈 Model Performance

The model achieves strong performance on the test set:

- **R² Score:** ~0.85 (model explains 85% of variance)
- **RMSE:** Low prediction error
- **MAE:** Consistent accuracy across predictions

Performance visualizations are saved in `reports/` directory.

## 🎨 Visualizations

The project generates comprehensive visualizations:

1. **EDA Visualizations:**
   - Price trends over time
   - Volume analysis
   - Correlation heatmaps
   - Distribution plots

2. **Model Evaluation:**
   - Actual vs Predicted scatter plot
   - Residual plots
   - Error distribution
   - Time series comparison

3. **Feature Importance:**
   - Top feature rankings
   - Importance scores

## 📝 Documentation

Comprehensive documentation is available in the `reports/` directory:

- **HLD.md:** System architecture and design
- **LLD.md:** Module-level implementation details
- **Pipeline_Architecture.md:** Step-by-step ML pipeline
- **EDA_Report.md:** Data analysis insights
- **Final_Report.md:** Complete project summary

## 🛠️ Technologies Used

- **Python 3.8+**
- **pandas** - Data manipulation
- **numpy** - Numerical computing
- **scikit-learn** - Machine learning
- **matplotlib & seaborn** - Static visualizations
- **plotly** - Interactive visualizations
- **streamlit** - Web application framework

## 📦 Key Components

### 1. Data Preprocessing (`preprocessing.py`)
- Handles missing values intelligently
- Ensures data quality and consistency
- Removes outliers and anomalies
- Prepares data for feature engineering

### 2. Feature Engineering (`feature_engineering.py`)
- Creates 14+ technical indicators
- Implements financial analysis techniques
- Generates target variable (7-day volatility)
- Handles time-series specific transformations

### 3. Model Training (`train_model.py`)
- Time-series aware data splitting
- Hyperparameter tuning with GridSearchCV
- Feature scaling for optimal performance
- Model persistence for deployment

### 4. Model Evaluation (`evaluate_model.py`)
- Comprehensive metric calculation
- Visualization generation
- Feature importance analysis
- Report creation

### 5. Deployment (`app.py`)
- User-friendly web interface
- Real-time predictions
- Interactive visualizations
- CSV download functionality

## 🎓 Learning Outcomes

This project demonstrates:
- Complete ML pipeline development
- Time-series data handling
- Feature engineering for financial data
- Model training and hyperparameter tuning
- Model evaluation and interpretation
- Web application deployment
- Professional code organization
- Comprehensive documentation

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 📞 Contact

For questions or feedback, please open an issue in the GitHub repository.

---

**Note:** This is a student project for educational purposes as part of PW Skills curriculum.
