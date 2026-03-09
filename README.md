# Forest Cover Type Classification
A comprehensive machine learning project that predicts forest cover types using cartographic and environmental features from the UCI Covertype dataset. Achieved **95%+ accuracy** using ensemble methods and advanced feature engineering.

## 📋 Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Dataset](#dataset)
- [Installation](#installation)
- [Usage](#usage)
- [Results](#results)
- [Project Structure](#project-structure)
- [Technologies](#technologies)
- [Key Learnings](#key-learnings)
- [Future Improvements](#future-improvements)
- [Author](#author)
- [License](#license)

## Overview

This project tackles a **multi-class classification problem** to predict forest cover types based on 54 cartographic features. The goal is to help forest management by automating the classification of forest areas, which traditionally requires manual surveying.

### Business Impact
- **Automated forest classification** reducing manual survey costs
- **95%+ prediction accuracy** enabling reliable forest management decisions
- **Feature importance analysis** identifying key environmental factors

##  Features

### Core Functionality
-  **Multi-class classification** (7 forest cover types)
-  **Multiple ML algorithms** comparison (Random Forest, XGBoost)
-  **Hyperparameter optimization** using GridSearchCV
-  **Comprehensive evaluation** with confusion matrices and metrics
-  **Feature importance analysis** for interpretability

### Technical Highlights
- Handles **581,012 samples** with 54 features efficiently
- Proper **train-test stratification** for balanced evaluation
- **Feature scaling** for continuous variables
- **One-hot encoded** categorical features handling
- **Cross-validation** for robust model selection

## Dataset

**Source:** [UCI Covertype Dataset](https://archive.ics.uci.edu/ml/datasets/covertype)

**Size:** 581,012 samples × 54 features

**Features:**
- **Continuous (10):** Elevation, Aspect, Slope, Horizontal/Vertical distance to hydrology, Hillshade (9am, noon, 3pm), Distance to roadways, Distance to fire points
- **Binary (44):** Wilderness Area (4 types), Soil Type (40 types)

**Target:** 7 forest cover types
1. Spruce/Fir
2. Lodgepole Pine
3. Ponderosa Pine
4. Cottonwood/Willow
5. Aspen
6. Douglas-fir
7. Krummholz

## Installation

### Prerequisites
```bash
Python 3.8+
pip or conda
```

### Setup
```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/forest-cover-classification.git
cd forest-cover-classification

# Install dependencies
pip install -r requirements.txt

# Or using conda
conda env create -f environment.yml
conda activate forest-cover
```

### Dependencies
```
pandas>=1.3.0
numpy>=1.21.0
scikit-learn>=1.0.0
xgboost>=1.5.0
matplotlib>=3.4.0
seaborn>=0.11.0
```

## Usage

### Google Colab (Recommended)
1. Open `forest_cover_classification_colab.ipynb` in Google Colab
2. Click **Runtime → Run all**
3. Results will be generated automatically

### Local Jupyter Notebook
```bash
jupyter notebook forest_cover_classification.ipynb
```

### Python Script
```bash
python forest_cover_classification.py
```

### Quick Start Example
```python
from sklearn.datasets import fetch_covtype
from sklearn.ensemble import RandomForestClassifier

# Load data
covertype = fetch_covtype(as_frame=True)
X, y = covertype.data, covertype.target

# Train model
model = RandomForestClassifier(n_estimators=100, random_state=42)
model.fit(X_train, y_train)

# Evaluate
accuracy = model.score(X_test, y_test)
print(f"Accuracy: {accuracy:.4f}")
```

##  Results

### Model Performance

| Model | Accuracy | F1-Score | Training Time |
|-------|----------|----------|---------------|
| **Random Forest** | **95.2%** | 0.951 | ~3 min |
| **XGBoost** | **95.8%** | 0.957 | ~4 min |
| Random Forest (tuned) | **96.1%** | 0.960 | ~15 min |
| XGBoost (tuned) | **96.3%** | 0.962 | ~20 min |

### Key Metrics
- ✅ **Best Accuracy:** 96.3% (XGBoost with tuning)
- ✅ **Cross-validation Score:** 95.8% (±0.4%)
- ✅ **Training Time:** <5 minutes (baseline models)
- ✅ **Prediction Time:** <1 second for 100k samples

### Confusion Matrix
![Confusion Matrix](images/confusion_matrix.png)

### Feature Importance (Top 10)
1. Elevation (23.4%)
2. Horizontal_Distance_To_Roadways (8.7%)
3. Horizontal_Distance_To_Fire_Points (7.2%)
4. Vertical_Distance_To_Hydrology (6.8%)
5. Hillshade_Noon (5.3%)
6. Soil_Type_10 (4.9%)
7. Wilderness_Area_3 (4.2%)
8. Horizontal_Distance_To_Hydrology (3.8%)
9. Hillshade_3pm (3.5%)
10. Aspect (3.1%)

### Visualizations
- Confusion matrices for both models
- Feature importance rankings
- Model performance comparison charts
- Class distribution analysis

##  Project Structure

```
forest-cover-classification/
│
├── notebooks/
│   ├── forest_cover_classification_colab.ipynb
│   └── forest_cover_classification.ipynb
│
├── src/
│   ├── forest_cover_classification.py
│   ├── data_preprocessing.py
│   ├── model_training.py
│   └── evaluation.py
│
├── images/
│   ├── confusion_matrix.png
│   ├── feature_importance.png
│   └── model_comparison.png
│
├── requirements.txt
├── environment.yml
├── README.md
└── LICENSE
```

## 🛠️ Technologies

**Programming Language:**
- Python 3.8+

**Machine Learning:**
- scikit-learn (Random Forest, evaluation metrics)
- XGBoost (gradient boosting)
- NumPy (numerical computing)

**Data Processing:**
- Pandas (data manipulation)
- StandardScaler (feature scaling)

**Visualization:**
- Matplotlib (plotting)
- Seaborn (statistical visualizations)

**Development:**
- Jupyter Notebook
- Google Colab

## Key Learnings

### Technical Skills
1. **Multi-class Classification** - Handling 7 different target classes
2. **Ensemble Methods** - Random Forest and XGBoost implementation
3. **Hyperparameter Tuning** - GridSearchCV optimization
4. **Feature Engineering** - Handling mixed data types
5. **Model Evaluation** - Confusion matrices, precision, recall, F1-score
6. **Big Data Handling** - Processing 580k+ samples efficiently

### Domain Knowledge
- Forest ecology and environmental factors
- Cartographic feature interpretation
- Wilderness area classification
- Soil type analysis

### Best Practices
- Train-test stratification for imbalanced classes
- Feature scaling for tree-based models
- Cross-validation for model selection
- Proper evaluation metrics for multi-class problems

## Future Improvements

- [ ] Implement deep learning models (Neural Networks)
- [ ] Add SHAP values for better interpretability
- [ ] Create interactive visualizations with Plotly
- [ ] Deploy model as REST API using Flask/FastAPI
- [ ] Build web dashboard for predictions
- [ ] Add real-time prediction capability
- [ ] Implement ensemble stacking methods
- [ ] Optimize for inference speed

## Author

**Omar Elnagar**
- LinkedIn: www.linkedin.com/in/omar-elnagar00
- Email: omar00alnagar@gmail.com

## License

This project is licensed under the MIT License - see the [LICENSE] file for details.

##  Acknowledgments

- UCI Machine Learning Repository for the Covertype dataset
- Scikit-learn and XGBoost development teams

## Contact

Feel free to reach out if you have questions or suggestions!

---

**⭐ If you found this project helpful, please consider giving it a star!**

