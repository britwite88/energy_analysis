# Energy Consumption Analysis

> A comprehensive data science project analyzing residential energy consumption patterns in northeastern Mexico using machine learning approaches.

**Author:** Samuel  
**Date:** August 8, 2025  
**Status:** ✅ Complete  

[![R](https://img.shields.io/badge/R-276DC3?style=flat&logo=r&logoColor=white)](https://www.r-project.org/)
[![Machine Learning](https://img.shields.io/badge/ML-Random%20Forest%20%7C%20XGBoost%20%7C%20SVM-orange)](https://github.com/)
[![Data Science](https://img.shields.io/badge/Data%20Science-Time%20Series%20Analysis-blue)](https://github.com/)

## 📋 Table of Contents
- [🎯 Project Overview](#-project-overview)
- [📊 Dataset Description](#-dataset-description)
- [🔬 Methodology](#-methodology)
- [📈 Results](#-results)
- [🏁 Conclusions](#-conclusions)
- [🚀 Getting Started](#-getting-started)
- [📁 Project Structure](#-project-structure)
- [🛠️ Dependencies](#️-dependencies)
- [📞 Contact](#-contact)

## 🎯 Project Overview

This project analyzes energy consumption patterns in residential buildings located in the northeastern region of Mexico. The main goal is to understand the relationship between weather conditions and energy consumption patterns using advanced machine learning techniques.

### 🔍 Research Questions
- How do weather conditions affect residential energy consumption?
- What are the main factors influencing active power consumption?
- Can we predict energy consumption based on weather patterns?

### 🎯 Objectives
- ✅ Explore and visualize energy consumption patterns
- ✅ Identify outliers and data quality issues
- ✅ Build predictive models for energy consumption classification
- ✅ Compare different ML algorithms (Random Forest, SVM, Decision Trees, XGBoost)

### 🏆 Key Achievements
- **99.72% accuracy** with XGBoost model
- Analysis of **605,260 observations** with 19 features
- **Minute-resolution** time series analysis
- Comprehensive **weather impact** quantification

## 📊 Dataset Description

### 📍 Data Source
The dataset consists of energy consumption data from residential buildings in the urban area of northeastern Mexico, collected from a publicly accessible web domain.

### 📏 Dataset Characteristics
- **📊 Resolution:** One-minute time series data
- **🔢 Observations:** 605,260 records
- **📋 Variables:** 19 features
- **📅 Time Period:** 2022-2024
- **🏠 Location:** Northeastern Mexico (urban residential)

### 🗂️ Key Variables

| Variable | Type | Description | Role |
|----------|------|-------------|------|
| `active_power` | Numeric | Active power consumption | 🎯 **Target Variable** |
| `reactive_power` | Numeric | Reactive power | Predictor |
| `apparent_power` | Numeric | Apparent power | Predictor |
| `voltage` | Numeric | Voltage measurements | Predictor |
| `current` | Numeric | Current measurements | Predictor |
| `temp` | Numeric | Temperature (°C) | 🌡️ Weather |
| `feels_like` | Numeric | Perceived temperature | 🌡️ Weather |
| `humidity` | Numeric | Humidity percentage | 💧 Weather |
| `main` | Factor | Weather condition (8 levels) | ☀️ Weather |
| `description` | Factor | Detailed weather (16 levels) | ☁️ Weather |

## 🔬 Methodology

### 🧹 Data Preprocessing Pipeline

#### 1. Data Quality Assessment
- ✅ **Missing value analysis** - No missing values in original dataset
- ✅ **Duplicate detection** and removal
- ✅ **Outlier identification** using IQR method

#### 2. Feature Engineering
- 📅 **Date/time components** extraction
- ⏰ **Lag features** (1-minute, 1-hour, 1-day)
- 📊 **Rolling statistics** (moving averages, max values)
- 🌤️ **Weather interaction** terms

#### 3. Data Transformation
- 🎯 **Target categorization** (Low, Medium-Low, Medium-High, High)
- 🔧 **Categorical encoding** (dummy variables)
- 📏 **Numerical standardization** for SVM

### 🤖 Machine Learning Pipeline

#### 1. Feature Selection
- 🔍 **Recursive Feature Elimination (RFE)** with cross-validation
- 📈 **Correlation analysis**

#### 2. Model Training
- 🌳 **Random Forest** (baseline + hyperparameter tuned)
- ⚡ **Support Vector Machine (SVM)**
- 🌲 **Decision Trees**
- 🚀 **XGBoost**

#### 3. Model Evaluation
- 🔄 **5-fold cross-validation**
- 📊 **Confusion matrices**
- 📈 **Precision, Recall, F1-score**
- 📉 **ROC curves and AUC**

## 📈 Results

### 🏆 Model Performance Comparison

| Model | 🎯 Accuracy | ⚡ Precision | 🔍 Recall | 🎪 F1-Score | ⏱️ Training Time |
|-------|-------------|-------------|-----------|-------------|------------------|
| 🚀 **XGBoost** | **99.72%** | **0.997** | **0.997** | **0.997** | ~3 min |
| 🌳 Random Forest (Default) | 99.65% | 0.996 | 0.996 | 0.996 | ~2 min |
| 🌳 Random Forest (Tuned) | 99.60% | 0.996 | 0.996 | 0.996 | ~5 min |
| ⚡ SVM (Tuned) | 99.2% | 0.992 | 0.992 | 0.992 | ~10 min |
| ⚡ SVM (Baseline) | 98.5% | 0.985 | 0.985 | 0.985 | ~1 min |
| 🌲 Decision Tree | 96.33% | 0.963 | 0.963 | 0.963 | ~30 sec |

### 🔍 Key Findings

#### 🥇 Best Performing Model
**XGBoost** achieved the highest accuracy at **99.72%**

#### 🎯 Most Important Features
1. 📊 **Lag active power** (1-minute) - Most predictive
2. ⚡ **Current** - Strong electrical correlation  
3. 📈 **Apparent power** - Physical relationship
4. 🌡️ **Temperature × Hour interaction** - Weather timing

#### 📊 Class-wise Performance
- ✅ **Balanced performance** across all energy consumption classes
- ✅ **Minimal misclassification** between adjacent categories
- ✅ **Consistent results** across different models

#### 🔧 Feature Selection Impact
- 📉 **RFE reduced features** from 56 to 9 most important variables
- ✅ **Maintained performance** while reducing complexity
- ⚡ **Improved computational efficiency**

### 📊 Exploratory Data Analysis Insights

#### 📈 Distribution Patterns
- **Active Power:** Right-skewed, peak around 100 (moderate usage)
- **Temperature:** Bell-shaped, centered around 20°C
- **Humidity:** Symmetric distribution (40-60%)

#### 🔗 Correlation Analysis
- **Strong correlations:** Active power ↔ Current (r ≈ 0.98)
- **Physical relationships:** Confirmed electrical parameter correlations
- **Weather patterns:** Temperature ↔ Feels-like (r ≈ 0.99)

#### ⏰ Time Series Patterns
- **🌨️ Seasonal:** Higher consumption in winter
- **📅 Daily:** Peak usage 10:00-12:00 and 18:00-23:00  
- **📆 Weekly:** Different weekend vs weekday patterns

#### 🌤️ Weather Impact
- ☀️ **Clear/cloudy conditions:** Highest median active power
- ⛈️ **Thunderstorms:** Lowest energy consumption
- 🌡️ **Temperature:** Subtle positive relationship

## 🏁 Conclusions

### 🎯 Key Achievements
- ✅ **High Predictive Accuracy:** Successfully developed models with >99% accuracy for energy consumption classification
- ✅ **Feature Importance Identification:** Confirmed that current electrical parameters are the strongest predictors  
- ✅ **Weather Impact Quantification:** Demonstrated measurable but subtle weather effects on energy consumption
- ✅ **Temporal Pattern Recognition:** Identified clear daily and seasonal consumption patterns

### 🔬 Research Contributions
- 📊 Comprehensive analysis of minute-resolution energy consumption data
- 🛠️ Effective feature engineering techniques for time series energy data
- 📈 Comparative evaluation of multiple machine learning algorithms
- 💡 Practical insights for energy management and forecasting

### ⚠️ Limitations
1. **💻 Computational Constraints:** Analysis limited to 5% of full dataset
2. **🗺️ Geographic Scope:** Limited to northeastern Mexico region  
3. **🌤️ Weather Granularity:** Weather data may not capture micro-climate variations
4. **🏠 Missing Context:** Limited information about building characteristics and occupancy

### 🚀 Future Work Recommendations
1. **📊 Scale Analysis:** Implement distributed computing for full dataset analysis
2. **🏗️ Additional Features:** Incorporate building characteristics and occupancy data
3. **⚡ Real-time Prediction:** Develop streaming prediction system
4. **🔧 Energy Optimization:** Use insights for demand response and efficiency recommendations  
5. **🌍 Cross-regional Validation:** Extend analysis to other geographic regions

---

## 🚀 Getting Started

### 📋 Prerequisites
- R 4.5.1 or higher
- RStudio or VS Code with R extension
- At least 8GB RAM (recommended for full dataset)

### 🔧 Installation

1. **Clone the repository:**
```bash
git clone https://github.com/yourusername/energy-consumption-analysis.git
cd energy-consumption-analysis
```

2. **Install required R packages:**
```r
# Core packages
install.packages(c("dplyr", "ggplot2", "tidyr", "lubridate"))

# Machine learning packages  
install.packages(c("caret", "randomForest", "e1071", "rpart", "xgboost"))

# Analysis packages
install.packages(c("pROC", "MLmetrics", "Hmisc", "corrplot"))
```

3. **Run the analysis:**
```r
# Open project.Rmd in RStudio/VS Code
# Or run all chunks programmatically
rmarkdown::render("project .Rmd")
```

### 📊 Quick Start
```r
# Load the data
energy <- read.csv("data/energy_weather.csv")

# Basic exploration
summary(energy)
dim(energy)  # 605,260 × 19

# Run a simple model
library(randomForest)
model <- randomForest(active_power_class ~ ., data = energy_sample)
```

---

## 📁 Project Structure

```
Data_Science_Dissertation/
├── 📄 README.md                 # Project documentation  
├── 📊 project .Rmd              # Main R Markdown analysis
├── 📁 data/
│   └── 📈 energy_weather.csv   # Raw dataset (605K records)
├── 📁 models/                  # Saved model objects
│   ├── 🌳 random_forest.rds
│   ├── 🚀 xgboost_model.rds
│   └── ⚡ svm_model.rds
├── 📁 plots/                   # Generated visualizations
│   ├── 📊 distributions.png
│   ├── 📈 time_series.png
│   └── 🔗 correlations.png
├── 📁 reports/                 # Analysis outputs
│   ├── 📄 analysis_report.html
│   └── 📋 model_comparison.pdf
└── 📁 scripts/                 # Helper R scripts
    ├── 🧹 preprocessing.R
    ├── 🔧 feature_engineering.R
    └── 📊 visualization.R
```

---

## 🛠️ Dependencies

### 📦 Core R Packages
```r
# Data manipulation and visualization
library(dplyr)       # Data manipulation
library(ggplot2)     # Plotting
library(tidyr)       # Data tidying

# Time series analysis  
library(lubridate)   # Date/time handling
library(zoo)         # Time series objects
library(xts)         # Extended time series

# Machine learning
library(caret)       # Classification and regression training
library(randomForest) # Random forest algorithm
library(e1071)       # Support vector machines
library(rpart)       # Decision trees
library(xgboost)     # Gradient boosting

# Model evaluation
library(pROC)        # ROC analysis
library(MLmetrics)   # ML performance metrics

# Statistical analysis
library(Hmisc)       # Statistical functions
library(corrplot)    # Correlation plots
library(leaps)       # Feature selection
```

### 💻 System Requirements
- **OS:** Windows 10+, macOS 10.15+, or Linux
- **Memory:** 8GB RAM minimum, 16GB recommended
- **Storage:** 2GB free space
- **R Version:** 4.5.1 or higher

---

## 📞 Contact

**Author:** Samuel  
**Project:** Energy Consumption Analysis  
**Institution:** [Your Institution]  
**Email:** [your.email@domain.com]  

### 🤝 Contributing
Contributions, issues, and feature requests are welcome!  
Feel free to check the [issues page](https://github.com/yourusername/energy-consumption-analysis/issues).

### 📄 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

### 🙏 Acknowledgments
- Data source: Publicly accessible energy consumption dataset
- Weather data integration for comprehensive analysis  
- R community for excellent machine learning packages

---

<div align="center">

**⭐ Star this repo if you found it helpful!**

Made with ❤️ and R

![Visitors](https://visitor-badge.glitch.me/badge?page_id=yourusername.energy-consumption-analysis)

</div>