[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/GodsDonBleet/AI-ML-Hybrid-Threat-Detection-System/blob/main/ML_FP_OSVM.ipynb)

# AI-ML-Hybrid-Threat-Detection-System

This repository hosts the code and resources for a research project focused on building an adaptive, high-precision network intrusion detection system using advanced machine learning techniques.

In the face of exponentially increasing network traffic and sophisticated, evasive cyber threats (including zero-days), traditional signature-based defenses are becoming insufficient. This project addresses the critical need for automated systems capable of real-time analysis and accurate anomaly detection at internet scale, aiming to minimize false negatives (missed attacks) and false positives (wasted resources).

### Project Objectives:

* **Comprehensive Dataset Preprocessing:** Utilized the NSL-KDD dataset, performing robust feature engineering, one-hot encoding for categorical data, standardization, normalization, and dimensionality reduction via PCA to prepare optimal input for ML models.
* **Evaluation of Diverse Predictive Models:** Benchmarked a suite of machine learning algorithms, including:
    * **Supervised Classifiers:** Support Vector Machines (SVM) and Naive Bayes (NB) for classifying known attack types (e.g., DoS, Probe).
    * **Unsupervised Detectors:** One-Class Support Vector Machines (OC-SVM) and Deep Autoencoders for identifying novel threats and zero-day anomalies by modeling "normal" network behavior.
* **Hybrid Classification for Attack Segregation:** Developed and evaluated two-stage hybrid models to significantly enhance precision:
    * **Deep Autoencoders + SVM:** Autoencoders extract latent features, which SVM then uses to classify specific attack types.
    * **1-SVM + SVM:** A first 1-SVM isolates malicious traffic, followed by a second SVM that precisely categorizes attack types within the anomalous subset.

### Key Achievements & Effectiveness:

The hybrid models consistently outperformed standalone algorithms by 4–8%, demonstrating their superior robustness and accuracy in dynamic network environments. Notably, the 1-SVM + SVM hybrid achieved the highest accuracy of 97.96%, by decoupling anomaly detection from attack typing, which significantly reduced noise from benign traffic.

This research highlights the transformative potential of combining unsupervised anomaly detection with supervised precision to adapt to evolving threats, handle imbalanced datasets (e.g., rare attacks), and provide an early warning system that complements traditional cybersecurity tools.

### Challenges & Mitigation Strategies Explored:

The project also addressed common challenges in ML-driven cybersecurity:

* **Hyperparameter Sensitivity & Retraining Overhead:** Investigated the need for careful tuning and strategies for continuous model adaptation to data drift.
* **Context-Dependent Performance:** Acknowledged that models trained on one environment might not generalize perfectly, necessitating considerations for diverse deployments (e.g., corporate vs. IoT).
* **Explainability Challenges in Deep Learning:** Explored the "black box" nature of deep learning models and potential mitigation techniques for better interpretability.

Strategies such as feature selection (PCA), regularization (L1/L2, Dropout), algorithmic adjustments (ensemble learning, incremental learning), continual learning, and cross-validation were analyzed to enhance model robustness, efficiency, and adaptability.

### Future Work:

A promising direction involves constructing a more advanced ensemble system that synergistically combines the strengths of all individual models (SVM, 1-SVM, Deep Autoencoders, Naive Bayes) using techniques like model stacking, majority voting, or dynamic weighting. This aims for even higher accuracy, improved generalization, and adaptive threat coverage, while also considering computational overhead, class imbalance, and explainability in deployment.
