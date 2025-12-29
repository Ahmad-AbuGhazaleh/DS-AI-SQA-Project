# Defect Log - House Prices Regression Project

**Project:** DS&AI Projects - House Prices Regression  
**Student ID:** 202210221  
**Student Name:** Ahmad Abu Ghazaleh  
**Report Generated:** December 27, 2025

---

## Summary Statistics

- **Total Issues Reported:** 2
- **Issues Resolved:** 2
- **Issues Open:** 0
- **Resolution Rate:** 100%

---

## Defect Details

### Issue #3: Data Defect - Critical Data Loss (PoolQC/MiscFeature)
**Type:** Data Defect  
**Severity:** CRITICAL  
**Status:** ✅ CLOSED

**Description:**  
Including 'PoolQC' (99.5% missing) and 'MiscFeature' (96% missing) features caused catastrophic data loss (1460 → ~5 rows, 99.7% loss).

**Detection Phase:** Data Cleaning  
**Reported Date:** December 27, 2025  
**Resolved Date:** December 27, 2025  

**Root Cause:**
- PoolQC: 1453/1460 missing (99.5%)
- MiscFeature: 1406/1460 missing (96.3%)
- Using dropna() with these features eliminated nearly all data

**Resolution:**
- Removed PoolQC and MiscFeature from feature list
- Implemented median imputation for numerical features
- Implemented mode imputation for categorical features
- Data retention: 0.3% → 100%

**Related Documents:**
- Change Request: CR-003
- Impact Assessment: IA-003
- Branch: `bugfix/house-prices-data-loss`

---

### Issue #4: Model Defect - Random Forest Overfitting
**Type:** Model Defect / Overfitting  
**Severity:** Medium-High  
**Status:** ✅ CLOSED

**Description:**  
Random Forest exhibited severe overfitting with train RMSE $11,083 vs test RMSE $29,040 (gap: $17,956, 162% difference).

**Detection Phase:** Model Training  
**Reported Date:** December 27, 2025  
**Resolved Date:** December 27, 2025  

**Root Cause:**
- `max_depth=15` allowed overly complex trees
- No regularization parameters (min_samples_split, min_samples_leaf)
- Missing K-Fold Cross-Validation (violates SQA Plan)
- No feature scaling (affected linear models)

**Resolution:**
- Implemented StandardScaler for feature scaling
- Added K-Fold Cross-Validation (k=5) per SQA Plan
- Optimized RF hyperparameters:
  - max_depth: 15 → 10
  - Added min_samples_split=10
  - Added min_samples_leaf=4
- Overfitting gap reduced from 162% to <20%

**Related Documents:**
- Change Request: CR-004
- Impact Assessment: IA-004
- Branch: `optimization/house-prices-scaling-cv`

---

## Defect Categories Breakdown

| Category | Count | Percentage |
|----------|-------|------------|
| Data Defect | 1 | 50% |
| Model Defect | 1 | 50% |
| Code Error | 0 | 0% |

---

## Lifecycle Summary

| Phase | Issues Detected | Issues Resolved |
|-------|----------------|-----------------|
| Data Cleaning | 1 | 1 |
| Model Training | 1 | 1 |
| **Total** | **2** | **2** |

---

## Quality Metrics

- **Defect Detection Rate:** 2 defects found during development
- **Resolution Time:** Average 2-4 hours per defect
- **Rework Impact:** Minimal (isolated fixes)
- **Final Quality:** All models pass performance standards
- **SQA Compliance:** 100% (CV implemented, standards followed)

---

## Lessons Learned

1. **Data Quality:** Always check missing value percentages before feature selection
2. **Imputation Strategy:** Median/mode imputation is effective for <5% missing values
3. **Cross-Validation:** Essential for detecting overfitting early (SQA Plan requirement)
4. **Feature Scaling:** Critical for linear models, good practice overall
5. **Hyperparameter Tuning:** Prevents overfitting and improves generalization

---

**Report Compiled by:** Ahmad Abu Ghazaleh  
**Date:** December 27, 2025

---