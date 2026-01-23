🩺 AI-Based Pneumonia Screening from Chest X-Ray Images

Clinically calibrated deep learning system for pneumonia screening from chest X-ray images, with sensitivity-first tuning, probability calibration, and Grad-CAM interpretability.

📌 Project Overview

This project presents an end-to-end medical AI pipeline for screening pneumonia from chest X-ray (CXR) images.
Unlike accuracy-focused toy models, this system is designed with clinical safety, calibration, and interpretability as first-class objectives.

The final model is intended as a radiology triage / screening decision-support tool, not an autonomous diagnostic system.

🎯 Clinical Objective

Pneumonia is a time-sensitive condition where missed diagnoses carry higher risk than false alarms.
Accordingly, the model is calibrated to:

Prioritize high sensitivity (minimize missed pneumonia)

Produce meaningful probability estimates

Provide visual explanations aligned with lung anatomy

🧠 Model Summary

Architecture: DenseNet-121 (ImageNet-pretrained)

Task: Binary classification (NORMAL vs PNEUMONIA)

Input: Frontal chest X-rays (224 × 224)

Framework: PyTorch

A progressive unfreezing strategy was applied after identifying early model collapse when using a fully frozen backbone.

📊 Dataset

Source: Pediatric Chest X-Ray Pneumonia Dataset (Kaggle)

Split	Samples
Train	5,216
Validation	16
Test	624

Labels: Image-level, binary
Supervision: Weak (diagnosis-level, no localization)

Expected Biases

Pediatric-only population

Weak supervision and label noise

Class imbalance

Acquisition variability

These biases were explicitly considered during evaluation and interpretation.

📈 Performance (Test Set)
Discrimination

ROC AUC: 0.956

Screening Operating Point

Threshold selected to achieve ≈95% sensitivity.

Metric	Value
Sensitivity (Pneumonia Recall)	95.1%
Specificity (Normal Recall)	79.1%

Confusion Matrix

[[185  49]
 [ 19 371]]


This configuration prioritizes patient safety by minimizing missed pneumonia cases.

🎯 Calibration

Brier Score: 0.0919

Predicted probabilities are reasonably well-calibrated, enabling risk-based triage rather than simple binary alerts.

🔍 Interpretability (Grad-CAM)

Grad-CAM analysis demonstrates:

Normal CXRs: diffuse, bilateral lung attention

Pneumonia CXRs: localized, asymmetric activation in affected lung regions

No reliance on spurious artifacts (corners, labels, borders)

This supports the clinical plausibility of model predictions.

🏥 Intended Clinical Use

✅ Appropriate

Radiology screening / triage support

Case prioritization

Decision support under clinician supervision

❌ Not appropriate

Autonomous diagnosis

Treatment decisions

Use outside validated populations or imaging protocols

⚠️ Limitations

Single-dataset evaluation

Pediatric population only

Small validation set

Weak supervision

No external or prospective validation

These limitations define scope and guide future work.

🧪 Technologies Used

Python

PyTorch

Torchvision

NumPy

scikit-learn

Matplotlib

📁 Repository Structure (Recommended)
medical-ai-pneumonia-screening/
│
├── notebooks/
│   ├── data_loading.ipynb
│   ├── training.ipynb
│   ├── calibration.ipynb
│   ├── interpretability.ipynb
│
├── models/
│   └── densenet_cxr_pneumonia.pt
│
├── report/
│   └── medical_ai_report.pdf
│
├── README.md
├── .gitignore
└── LICENSE

📌 Key Takeaways

Medical AI success requires more than high accuracy

Sensitivity-first calibration is critical for screening tasks

Interpretability is mandatory for clinical trust

Deployment constraints define real-world value

📜 Disclaimer

This project is for educational and research purposes only.
It is not a medical device and must not be used for clinical diagnosis or treatment decisions.

👤 Author

[Oscar Kimeli]
Medical AI / Machine Learning
Portfolio project demonstrating end-to-end clinical AI development

