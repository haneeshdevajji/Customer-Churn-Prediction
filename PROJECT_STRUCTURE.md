# Project Folder Structure

## Recommended Clean Organization for ML Churn Prediction Project

```
customer-churn-prediction/
│
├── 📁 data/
│   └── WA_Fn-UseC_-Telco-Customer-Churn.csv    # Raw customer data (7,043 records)
│
├── 📁 images/
│   ├── final_model.png                         # Confusion matrix visualization
│   ├── model_comparison.png                    # Performance comparison plots
│   └── feature_importance.png                  # Feature importance chart
│
├── 📁 models/ (Optional - for production)
│   ├── svm_model.pkl                           # Trained model binary
│   ├── scaler.pkl                              # Fitted StandardScaler
│   └── label_encoder.pkl                       # LabelEncoder for features
│
├── 📁 notebooks/
│   ├── churn.ipynb                             # Main analysis notebook
│   ├── exploratory_analysis.ipynb              # EDA notebook (optional)
│   └── model_comparison.ipynb                  # Compare multiple algorithms (optional)
│
├── 📁 scripts/ (Optional - for production)
│   ├── preprocess.py                           # Data preprocessing functions
│   ├── train_model.py                          # Model training script
│   ├── predict.py                              # Batch prediction script
│   └── utils.py                                # Utility functions
│
├── 📁 results/
│   ├── metrics.json                            # Model performance metrics
│   ├── predictions.csv                         # Predictions on test set
│   └── evaluation_report.txt                   # Detailed evaluation summary
│
├── 📄 churn.ipynb                              # Main notebook (at root level)
│
├── 📄 README.md                                # Project documentation
│   ├─ Overview
│   ├─ Problem statement
│   ├─ Dataset description
│   ├─ Preprocessing steps
│   ├─ Model development
│   ├─ Results
│   ├─ How to run
│   └─ Future improvements
│
├── 📄 requirements.txt                         # Python dependencies
│   ├─ pandas>=1.3.0
│   ├─ numpy>=1.21.0
│   ├─ matplotlib>=3.4.0
│   ├─ seaborn>=0.11.0
│   ├─ scikit-learn>=0.24.0
│   ├─ imbalanced-learn>=0.8.0
│   └─ xgboost>=1.4.0
│
├── 📄 .gitignore                               # Git ignore rules
│   ├─ *.ipynb_checkpoints/
│   ├─ __pycache__/
│   ├─ *.pyc
│   ├─ venv/
│   └─ .DS_Store
│
└── 📄 LICENSE                                  # License information (MIT)
```

## Folder Descriptions

### `/data` - Data Storage
- **Purpose:** Store raw and processed datasets
- **Contents:**
  - Raw CSV files
  - Processed/cleaned data (optional)
  - Data dictionaries or metadata files
- **Note:** Add to `.gitignore` if files are large

### `/images` - Visualizations
- **Purpose:** Save all generated plots and visualizations
- **Contents:**
  - Confusion matrix
  - Performance comparisons
  - Feature importance plots
  - Distribution plots
- **Format:** PNG/JPG for reports, SVG for publications

### `/models` - Saved Models (Production)
- **Purpose:** Store trained model artifacts
- **Contents:**
  - Trained SVM model (.pkl)
  - Fitted scalers and encoders
  - Model metadata
- **Use:** For deployment and inference pipelines

### `/notebooks` - Jupyter Notebooks
- **Purpose:** Analysis and experimentation
- **Contents:**
  - Main analysis notebook
  - Exploratory data analysis (EDA)
  - Model comparison studies
- **Naming:** Descriptive names with version numbers (e.g., `v1_baseline.ipynb`)

### `/scripts` - Python Modules (Production)
- **Purpose:** Reusable, production-ready code
- **Contents:**
  - Data preprocessing functions
  - Model training pipeline
  - Prediction functions
  - Utility helpers
- **Structure:** Modular, well-tested, documented

### `/results` - Analysis Results
- **Purpose:** Store model outputs and reports
- **Contents:**
  - Performance metrics (JSON/CSV)
  - Predictions on test set
  - Evaluation reports
  - Cross-validation results

## Minimal Project Structure

For a quick start or small project, use this minimal version:

```
customer-churn-prediction/
├── data/
│   └── WA_Fn-UseC_-Telco-Customer-Churn.csv
├── images/
│   └── final_model.png
├── churn.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

## Full Production Structure

For deployment and team collaboration:

```
customer-churn-prediction/
├── data/
├── images/
├── models/
├── notebooks/
├── scripts/
├── results/
├── tests/                      # Unit tests
├── config/                     # Configuration files
│   └── config.yaml
├── .github/                    # GitHub workflows
│   └── workflows/
│       └── ci.yml
├── churn.ipynb
├── README.md
├── requirements.txt
├── setup.py                    # Package installation
├── .gitignore
├── .env.example                # Environment variables template
└── LICENSE
```

## Setup Instructions

### 1. Create the Folder Structure

```bash
# Create main directory
mkdir customer-churn-prediction
cd customer-churn-prediction

# Create subdirectories
mkdir data images models notebooks scripts results

# Create files
touch README.md requirements.txt .gitignore churn.ipynb LICENSE
```

### 2. Initialize Git Repository

```bash
git init
git add .
git commit -m "Initial project structure"
```

### 3. Set Up Python Environment

```bash
# Create virtual environment
python -m venv venv

# Activate (Windows)
venv\Scripts\activate

# Activate (macOS/Linux)
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

### 4. Add .gitignore Template

Create `.gitignore` with:

```
# Virtual environments
venv/
env/
ENV/

# Python
__pycache__/
*.py[cod]
*$py.class
*.so
.Python

# Jupyter
.ipynb_checkpoints/
*.ipynb_checkpoints

# IDE
.vscode/
.idea/
*.swp
*.swo
*~

# OS
.DS_Store
Thumbs.db

# Data (if sensitive)
# data/raw/
# data/processed/

# Model files
models/*.pkl
models/*.joblib

# Results
results/predictions.csv

# Environment
.env
.env.local
```

## Naming Conventions

### File Naming
- **Notebooks:** `analysis_churn_prediction.ipynb`, `v2_svm_tuning.ipynb`
- **Scripts:** `preprocess_data.py`, `train_svm_model.py`
- **Data:** `telco_churn_raw.csv`, `telco_churn_processed.csv`
- **Images:** `confusion_matrix_svm_v2.png`, `feature_importance_top10.png`

### Variable Naming
- **DataFrames:** `df_raw`, `df_processed`, `df_train`
- **Arrays:** `X_train`, `y_test`, `X_scaled`
- **Models:** `svm_model`, `rf_classifier`, `best_model`
- **Metrics:** `accuracy_score`, `precision_recall_score`

## Version Control Best Practices

### Useful .gitignore Patterns

```
# Large data files
*.csv
*.zip
*.tar.gz

# Model files
*.pkl
*.joblib
*.h5

# Virtual environments
venv/
.venv/

# IDE files
.vscode/
.idea/
*.swp

# Jupyter
.ipynb_checkpoints/

# macOS
.DS_Store

# Temporary files
*.tmp
*.bak
```

### Git Workflow

```bash
# Commit at logical checkpoints
git add data/
git commit -m "Add raw customer churn dataset"

git add churn.ipynb
git commit -m "Complete SVM model training and evaluation"

git add images/final_model.png
git commit -m "Add confusion matrix visualization"
```

## README Structure Template

```markdown
# Project Name

## Overview
[What is this project about?]

## Problem Statement
[What business problem does it solve?]

## Dataset
[Describe the data]

## Installation
[How to set up]

## Usage
[How to run]

## Results
[Key findings]

## Folder Structure
[Explain directory layout]

## Contributing
[How to contribute]

## License
[License information]
```

## Summary

✓ **Simple Setup:** Start with minimal structure  
✓ **Scalable:** Grow as project complexity increases  
✓ **Professional:** Follows industry best practices  
✓ **Collaborative:** Clear organization for team projects  
✓ **Maintainable:** Easy to navigate and update  

---

**Key Takeaway:** Organize from the start. A clean structure makes your project easier to understand, maintain, and scale.
