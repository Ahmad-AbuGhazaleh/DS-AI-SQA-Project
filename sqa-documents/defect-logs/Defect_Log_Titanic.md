# Defect Log - Titanic Survival Prediction Project

**Project:** DS&AI Projects - Titanic Survival Prediction  
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

### Issue #1: Data Defect - Excessive Data Loss
**Type:** Data Defect  
**Severity:** High  
**Status:** ✅ CLOSED

**Description:**  
Including 'Cabin' feature with 77% missing values caused excessive data loss (891 → 200 rows).

**Detection Phase:** Data Cleaning  
**Reported Date:** December 27, 2025  
**Resolved Date:** December 27, 2025  

**Resolution:**
- Removed 'Cabin' feature from selected features
- Implemented proper imputation for Age, Fare, Embarked
- Data retention improved to 79.9% (712 rows)

**Related Documents:**
- Change Request: CR-001
- Impact Assessment: IA-001
- Branch: `bugfix/titanic-cabin-data-loss`

---

### Issue #2: Model Defect - Low Recall Performance
**Type:** Model Defect / Optimization  
**Severity:** Medium  
**Status:** ✅ CLOSED

**Description:**  
Random Forest model had critically low recall (47.83%), failing to identify majority of survivors.

**Detection Phase:** Model Training  
**Reported Date:** December 27, 2025  
**Resolved Date:** December 27, 2025  

**Root Cause:**  
`max_depth=2` hyperparameter was too restrictive, causing underfitting.

**Resolution:**
- Optimized RF hyperparameters (max_depth=10, n_estimators=100)
- Added min_samples_split and min_samples_leaf for regularization
- Implemented K-Fold Cross-Validation (k=5)
- Recall improved from 47.83% to 65.22%
- F1-Score improved from 62.86% to 70.87%

**Related Documents:**
- Change Request: CR-002
- Impact Assessment: IA-002
- Branch: `optimization/titanic-rf-hyperparameters`

---

## Defect Categories Breakdown

| Category | Count | Percentage |
|----------|-------|------------|
| Data Defect | 1 | 50% |
| Model Defect | 1 | 50%  |
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

- **Defect Detection Rate:** 2 defects found during desk checks
- **Resolution Time:** Average 2-4 hours per defect
- **Rework Required:** Minimal (isolated fixes)
- **Final Quality:** All models pass SQA baseline requirements

---

**Report Compiled by:** Ahmad Abu Ghazaleh  
**Date:** December 27, 2025

---