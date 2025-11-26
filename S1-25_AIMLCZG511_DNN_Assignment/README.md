# DNN_Breast_Cancer_Wisconsin_Diagnostic
Deep Neural Networks Assignment
# Project & Environment Setup
# 1. create project folder and venv
mkdir DNN_Breast_Cancer_Wisconsin_Diagnostic && cd DNN_Breast_Cancer_Wisconsin_Diagnostic
# [No Need to learn any internal just commands to start the process]
python3 -m venv .venv
# 2. activate venv (mac/linux)[No Need to learn]
source .venv/bin/activate
# on Windows (PowerShell): 
.venv\Scripts\Activate.ps1

# install only allowed libraries (no sklearn models, no TF/PyTorch) [No Need to learn]
pip install --upgrade pip
pip install numpy pandas matplotlib jupyterlab

# create folders
mkdir data notebooks outputs
# start jupyterlab (or open VSCode notebook)
jupyter lab (started)







# 1. Project Title

DNN Assignment – Breast Cancer Wisconsin Diagnostic Dataset

# 2. Student Details

Student ID: 2025aa05599

Course: Deep Neural Networks

Institute: BITS Pilani

# 3. Dataset Description

The Breast Cancer Wisconsin Diagnostic Dataset consists of 568 samples and 30 real-valued features describing tumor characteristics (radius, texture, concavity, smoothness, etc.).
Each sample is labeled as:

1 = Malignant (M)

0 = Benign (B)

This is a binary classification task.

# 4. Preprocessing Steps

Loaded dataset (CSV) without headers.

Assigned 32 correct column names (1 ID + 30 features + diagnosis).

Converted labels: M → 1, B → 0.

Dropped id column.

Implemented custom StandardScaler (mean/std using NumPy only).

Implemented custom train-test split (80/20) without sklearn.

Final shapes:

Train: 455 × 30

Test: 113 × 30

# 5. Baseline Model – Logistic Regression (NumPy)

Built completely from scratch:

Sigmoid activation

Binary cross-entropy loss

Manual gradient descent

No sklearn functions

Baseline Results
Metric	Value
Training Time	0.0898 s
Test BCE Loss	0.1468
Test Accuracy	0.9646
Precision	0.9773
Recall	0.9348
F1-Score	0.9556

# 6. MLP Model – From Scratch (NumPy)
Architecture

Input: 30 features

Hidden Layer: 64 neurons (ReLU)

Output Layer: 1 neuron (Sigmoid)

Optimizer: Mini-batch SGD

Loss: Binary Cross-Entropy

Epochs: 500

L2 Regularization: 1e-4

MLP Results
Metric	Value
Training Time	0.3083 s
Test BCE Loss	0.1531
Test Accuracy	0.9557
Precision	0.9767
Recall	0.9138
F1-Score	0.9438

# 7. Final get_assignment_results() Output

(This is exactly what the BITS autograder will read.)

{
 "dataset_name": "Breast Cancer Wisconsin Diagnostic",
 "n_samples": 568,
 "n_features": 31,
 "problem_type": "binary_classification",
 "primary_metric": "f1",

 "baseline_model": {
     "test_accuracy": 0.9646,
     "test_f1": 0.9556,
     "training_time_seconds": 0.0898
 },

 "mlp_model": {
     "architecture": "MLP hidden_layers=[64]",
     "test_accuracy": 0.9557,
     "test_f1": 0.9438,
     "training_time_seconds": 0.3083
 }
}