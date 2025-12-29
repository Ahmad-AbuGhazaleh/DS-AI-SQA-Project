# DS&AI Projects - Software Quality Assurance Implementation

**Student ID:** 202210221  
**Student Name:** Ahmad Abu Ghazaleh  
**Department:** Software Engineering  
**Course:** Software Quality Management & Process Improvement (603490)

---

## Project Overview

This repository demonstrates comprehensive Software Quality Assurance (SQA) practices applied to three machine learning projects:

1. ✅ **Titanic Survival Prediction** - Classification (COMPLETED)
2. ✅ **House Prices Regression** - Regression (COMPLETED)
3. ✅ **Sentiment140 Analysis** - NLP Sentiment Classification (COMPLETED)

---

## Repository Structure
```
DS-AI-SQA-Project/
│
├── titanic-survival-prediction/
│   ├── titanic_survival_prediction.ipynb
│   ├── titanic_performance_report.csv
│   ├── titanic_data_quality_report.png
│   └── titanic_confusion_matrices.png
│
├── house-prices-regression/          (Coming soon)
├── sentiment140-analysis/             (Coming soon)
│
├── sqa-documents/
│   ├── change-requests/
│   │   ├── CR-001_Titanic_Cabin_Feature_Removal.docx
│   │   └── CR-002_Titanic_RF_Hyperparameter_Optimization.docx
│   │
│   ├── impact-assessments/
│   │   ├── IA-001_Titanic_Cabin_Feature_Impact.docx
│   │   └── IA-002_Titanic_RF_Optimization_Impact.docx
│   │
│   ├── defect-logs/
│   │   └── Defect_Log_Titanic.md
│   │
│   └── Configuration_Audit_Titanic.md
│
├── datasets/
│   └── titanic/
│       ├── train.csv
│       └── test.csv
│
├── requirements.txt
├── .gitignore
└── README.md
```

---

## SQA Activities Implemented

### ✅ Part A: SQA Plan
- Data Integrity Testing (Unit Testing)
- Model Validation (Performance Testing)
- Desk Checks (Self-Revision)
- Configuration Audits
- PEP 8 Coding Standards
- IEEE 829 Documentation Standards
- Error Reporting & Tracking via GitHub Issues

### ✅ Part B: SQA Case Tool Demonstration (Git/GitHub)
- **Change Control:** 2 change requests (CR-001, CR-002)
- **Defect Tracking:** 2 issues tracked and closed (#1, #2)
- **Audits:** Configuration audit completed
- **Performance Reporting:** Comprehensive metrics and visualizations
- **Version Control:** Feature, bugfix, and optimization branches

---

## Titanic Project Results

### Performance Metrics
| Model | Accuracy | Precision | Recall | F1-Score | CV Accuracy |
|-------|----------|-----------|--------|----------|-------------|
| Logistic Regression | 80.45% | 79.31% | 66.67% | 72.44% | 79.78% ± 3.80% |
| Random Forest | 79.33% | 77.59% | 65.22% | 70.87% | 81.75% ± 4.91% |

✅ **Both models pass SQA baseline requirement (≥70% accuracy)**

### SQA Documentation
- 2 Change Requests (CR-001, CR-002)
- 2 Impact Assessments (IA-001, IA-002)
- 2 GitHub Issues resolved
- 2 Desk Checks completed
- 1 Configuration Audit passed

---

## House Prices Project Results

### Performance Metrics
| Model | Test RMSE | Test R² | Test MAE | Overfitting Gap | CV RMSE |
|-------|-----------|---------|----------|-----------------|---------|
| **Lasso Regression** | **$34,469** | **0.8451** | **$19,724** | **9.2%** | **$35,078 ± $8,424** |
| Ridge Regression | $34,470 | 0.8451 | $19,735 | 9.3% | $35,164 ± $8,409 |
| Linear Regression | $34,567 | 0.8442 | $19,776 | 9.8% | $35,475 ± $8,433 |
| Random Forest | $38,278 | 0.8090 | $20,980 | 21.1% | $34,115 ± $5,564 |

✅ **Best model: Lasso Regression - Explains 84.51% of price variance**

### SQA Documentation
- 2 Change Requests (CR-003, CR-004)
- 2 Impact Assessments (IA-003, IA-004)
- 2 GitHub Issues resolved (#3, #4)
- 2 Desk Checks completed
- 1 Configuration Audit passed

---
## Sentiment140 Project Results

### Performance Metrics
| Model | Test Accuracy | Precision | Recall | F1-Score | CV Accuracy | SQA Status |
|-------|---------------|-----------|--------|----------|-------------|------------|
| **Logistic Regression** | **71-72%** | **0.75** | **0.66** | **0.70** | **~0.70** | **✅ PASS** |
| Naive Bayes | 68% | 0.70 | 0.64 | 0.67 | ~0.68 | Close |
| Linear SVM | 69% | 0.71 | 0.65 | 0.68 | ~0.69 | Close |

✅ **Best model: Logistic Regression - Passes SQA baseline (≥70%)**

### NLP Pipeline
- **Dataset:** 1.6M tweets (1000 sample for development)
- **Preprocessing:** Text cleaning, normalization
- **Feature Extraction:** TF-IDF with 1150 features + bigrams
- **Class Balance:** Perfect 50/50 split (stratified sampling)
- **Regularization:** L2 (C=0.5) to prevent overfitting

### SQA Documentation
- 2 Change Requests (CR-005, CR-006)
- 2 Impact Assessments (IA-005, IA-006)
- 2 GitHub Issues resolved (#5, #6)
- 3 Desk Checks completed
- 1 Configuration Audit passed

---

## Getting Started

### Prerequisites
- Python 3.8+
- Jupyter Notebook or VS Code with Jupyter extension
- Git

### Installation
```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/DS-AI-SQA-Project.git
cd DS-AI-SQA-Project

# Install dependencies
pip install -r requirements.txt

# Open Jupyter Notebook
jupyter notebook titanic-survival-prediction/titanic_survival_prediction.ipynb
```

---

## Branch Strategy

- `main` - Stable production code
- `feature/*` - New feature development
- `bugfix/*` - Bug fixes
- `optimization/*` - Performance optimizations

---

## Standards & Compliance

- **Coding:** PEP 8 (Python Enhancement Proposal 8)
- **Documentation:** IEEE 829 (Adapted for ML)
- **Version Control:** Git Feature Branch Workflow
- **Issue Tracking:** GitHub Issues

---

## Contact

**Ahmad Abu Ghazaleh**  
Student ID: 202210221  
Department of Software Engineering

---

## License

This project is for academic purposes as part of the Software Quality Management course.

---

**Last Updated:** December 27, 2025