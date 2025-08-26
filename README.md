# Air Quality Model Performance Comparison

This project provides a comprehensive analysis comparing Linear Regression, Decision Tree, and Random Forest algorithms for air quality prediction using temporal pattern analysis.

## 🎯 Project Objective
To compare the performance of different machine learning algorithms for predicting Benzene (C6H6) concentration and analyze temporal patterns in air quality data.

## 📊 Dataset Information
- **Source**: UCI ML Air Quality Dataset  
- **Size**: 9,471 observations × 17 features
- **Temporal Range**: Hourly measurements
- **Target Variable**: C6H6(GT) - Benzene concentration
- **Features**: CO, NOx, NO2 levels, temperature, humidity, sensor data

## 🔧 Technologies Used
```python
pandas==1.5.0
numpy==1.23.0
scikit-learn==1.1.0
matplotlib==3.6.0
seaborn==0.12.0
scipy==1.9.0
```

## 🔍 Analysis Performed
### Exploratory Data Analysis (EDA)
- ✅ Data distributions and histogram analysis
- ✅ Correlation matrix calculation
- ✅ Temporal pattern analysis (hourly/daily/weekly)
- ✅ Relationships between pollutants and weather variables
- ✅ Outlier detection and box plot analysis

### Data Preprocessing
- Missing value imputation (median strategy)
- Feature engineering (hour, day, month, day of week)
- StandardScaler normalization
- Time-series aware train/test split (70%-30%)

## 🤖 Models Compared
1. **Linear Regression**: Basic linear model
2. **Decision Tree Regressor**: Non-linear pattern capture
3. **Random Forest Regressor**: Ensemble learning (100 estimators)

## 📊 Model Performance Results

| Model | MSE | RMSE | MAE | R² |
|-------|-----|------|-----|-----|
| **Decision Tree** | 0.0021 | 0.0462 | 0.0115 | **0.999999** |
| **Random Forest** | 0.0032 | 0.0565 | 0.0128 | **0.999999** |
| **Linear Regression** | 15.9253 | 3.9906 | 3.6325 | 0.9949 |

## 🎯 Key Findings
- **Strongest Correlations**:
  - C6H6(GT) ↔ AH (Absolute Humidity): r = 0.9846
  - C6H6(GT) ↔ Temperature: r = 0.9714
  - NOx(GT) ↔ NO2(GT): r = 0.8171

- **Temporal Patterns**: Distinct hourly and weekly cycles in pollutant levels

- **Model Performance**: Tree-based models achieved exceptionally high accuracy (R² ≈ 1.0)

## ⚠️ Analysis Notes
The extremely high R² values (0.999999) may indicate:
- Strong feature-target correlations
- Potential overfitting
- Pattern similarity in time-series data

## 🚀 Installation & Usage

### Requirements
```bash
pip install pandas numpy scikit-learn matplotlib seaborn scipy
```

### Data Download
Download the dataset from Kaggle:
```bash
kaggle datasets download -d fedesoriano/air-quality-data-set
```

### Execution
```bash
python air_quality.py
```

## 📁 Project Structure
```
air-quality-ml-comparison/
├── air_quality.py                    # Main analysis code
├── data/
│   └── AirQuality.csv               # Raw data
├── results/
│   ├── correlation_heatmap.png      # Correlation matrix
│   ├── model_comparison.png         # Model comparison
│   ├── feature_importance.png       # Feature importance ranking
│   └── temporal_patterns.png        # Time series plots
└── README.md
```

## 📈 Technical Details
- **Data Split**: Time-aware split (temporal order preserved)
- **Feature Engineering**: Time-based features added
- **Scaling**: StandardScaler applied
- **Evaluation**: MSE, RMSE, MAE, R² metrics used

## 📚 Key Insights
1. **Decision Tree Performance**: Achieved the lowest error metrics with near-perfect R² score
2. **Random Forest Robustness**: Slightly higher errors but still excellent performance
3. **Linear Model Limitations**: Higher errors indicate non-linear relationships in data
4. **Feature Importance**: Weather variables (temperature, humidity) are strong predictors
5. **Temporal Dependencies**: Clear patterns in hourly and weekly pollution cycles

## 🔬 Research Applications
This analysis can be valuable for:
- Environmental monitoring systems
- Air quality prediction models
- Urban planning and policy decisions
- Public health assessments
- Industrial emission control

## 👤 Developer
- **Kaggle**: [@kurkigal](https://www.kaggle.com/kurkigal)

## 📄 License
MIT License

## 🤝 Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

---
⭐ If you found this project helpful, please consider giving it a star!