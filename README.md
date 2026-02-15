# Project Title

Medical AI for Pneumonia Screening

## Project Description
This project leverages deep learning techniques to develop an AI model that can screen for pneumonia in chest X-ray images effectively. The model aims to support healthcare professionals in providing faster and more accurate diagnoses.

## Calibration
### ROC Curve
The Receiver Operating Characteristic (ROC) curve showcases the diagnostic ability of the model at various threshold settings. AUC (Area Under the Curve) values close to 1 signify a strong performance.

### Calibration Curves
The calibration curves illustrate how well the predicted probabilities of pneumonia align with actual occurrences. A well-calibrated model should follow a 45-degree line.

## Confusion Matrix
The confusion matrix displays the performance metrics, providing insights on true positives, false positives, true negatives, and false negatives. 

### Clinical Interpretation
In this context:  
- **True Positive (TP)**: Correctly identified pneumonia cases.  
- **False Positive (FP)**: Incorrectly identified pneumonia cases.  
- **True Negative (TN)**: Correctly identified non-pneumonia cases.  
- **False Negative (FN)**: Missed pneumonia cases that were present.  

Effective management of these metrics is crucial in clinical settings to minimize false negatives that could lead to untreated pneumonia cases.

## Interpretability: Grad-CAM Visual Explanations
To enhance the interpretability of the model's predictions, Grad-CAM visualizations are employed. These visual explanations help in understanding the areas of the X-ray images the model focused on when making predictions.

![Grad-CAM Visualization](report/figures/gradcam_example_1.png)
![Grad-CAM Visualization](report/figures/gradcam_example_2.png)
![Grad-CAM Visualization](report/figures/gradcam_example_3.png)