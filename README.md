# Pneumonia Screening Using AI

## A Comprehensive Approach to Diagnosis and Treatment

This project leverages advanced AI techniques to enhance the screening process for pneumonia, aiming to improve patient outcomes and streamline clinical workflows. The tool is designed for healthcare professionals seeking to integrate AI-driven solutions into their practice.

## Calibration

Evaluation Plots

ROC Curve
![ROC Curve](report/figures/roc_curve.png)

Calibration Curve
![Calibration Curve](report/figures/calibration_curve.png)

---

## Confusion Matrix

Model performance across classification outcomes:

![Confusion Matrix](report/figures/confusion_matrix.png)

Interpretation:

- True Negatives (TN): Correct NORMAL predictions  
- True Positives (TP): Correct PNEUMONIA detections  
- False Negatives (FN): Missed pneumonia cases (clinical risk)  
- False Positives (FP): Overcalls requiring review  

Sensitivity-first calibration reduces FN at the cost of moderate FP — appropriate for screening deployment.

---

## Interpretability — Grad-CAM Visual Explanations

Grad-CAM highlights anatomical regions influencing model predictions, improving clinical transparency.

### Normal Case

![Grad-CAM Normal](report/figures/gradcam_normal.png)

Model attention is diffuse without focal consolidation signals.

---

### Pneumonia Case

![Grad-CAM Pneumonia](report/figures/gradcam_pneumonia.png)

Activation localizes to parenchymal opacification regions consistent with pneumonia patterns.