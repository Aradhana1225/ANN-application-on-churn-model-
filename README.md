# Customer Churn Prediction using Artificial Neural Network

An end-to-end **Customer Churn Prediction** project built with **TensorFlow/Keras**. The project uses an Artificial Neural Network (ANN) to predict whether a bank customer is likely to leave the bank based on demographic, financial, and account-related attributes.

## 📌 Project Overview

Customer churn prediction helps organizations identify customers who are at risk of leaving so that appropriate retention strategies can be planned.

This project demonstrates a complete machine learning workflow:

- Loading and exploring customer data
- Separating independent and dependent variables
- Encoding categorical features
- Splitting data into training and testing sets
- Standardizing numerical features
- Building an Artificial Neural Network
- Training the model with validation data
- Using Early Stopping
- Generating churn predictions
- Evaluating performance using a confusion matrix and accuracy
- Visualizing training/validation accuracy and loss

## 🎯 Objective

The objective is to predict the `Exited` variable:

| Value | Meaning |
|---|---|
| `0` | Customer did not leave |
| `1` | Customer left |

This makes the task a **binary classification problem**.

## 📊 Dataset

The notebook loads the dataset from:

```text
Churn_Modelling.csv
```

The dataset contains **10,000 customer records**.

The input features used in the notebook include:

- CreditScore
- Geography
- Gender
- Age
- Tenure
- Balance
- NumOfProducts
- HasCrCard
- IsActiveMember
- EstimatedSalary

The target variable is:

```text
Exited
```

### Feature Engineering

The categorical variables `Geography` and `Gender` are converted into numerical representations using **one-hot encoding**, with the first category dropped.

The resulting feature matrix contains **11 input features**.

## 🧠 Model Architecture

The project uses a feed-forward Artificial Neural Network implemented with Keras `Sequential`.

```text
Input Layer
11 neurons
    ↓
Dense Layer
7 neurons — ReLU
    ↓
Dense Layer
6 neurons — ReLU
    ↓
Output Layer
1 neuron — Sigmoid
```

### Why these activations?

- **ReLU** is used in the hidden layers to introduce non-linearity.
- **Sigmoid** is used in the output layer because the task is binary classification and the model produces a probability between 0 and 1.

## ⚙️ Training Configuration

The notebook uses:

| Parameter | Configuration |
|---|---|
| Framework | TensorFlow / Keras |
| Optimizer | Adam |
| Learning Rate | 0.01 |
| Loss Function | Binary Crossentropy |
| Metric | Accuracy |
| Batch Size | 10 |
| Maximum Epochs | 1000 |
| Validation Split | 33% of training data |
| Early Stopping | Enabled |
| Early Stopping Patience | 20 |
| Classification Threshold | 0.5 |

The dataset is split into:

- **80% training data**
- **20% test data**

Feature scaling is performed using `StandardScaler`.

## 📈 Model Performance

On the test set, the notebook reports:

**Accuracy: 85.55%**

The resulting confusion matrix is:

```text
[[1495, 100],
 [ 189, 216]]
```

Interpreted as:

```text
                 Predicted
                 0       1

Actual  0      1495    100
Actual  1       189    216
```

The notebook also visualizes:

- Training vs. validation accuracy
- Training vs. validation loss

These plots help understand the model's learning behaviour during training.

## 🛠️ Technologies Used

- **Python**
- **TensorFlow**
- **Keras**
- **NumPy**
- **Pandas**
- **Matplotlib**
- **Scikit-learn**
- **Google Colab / Jupyter Notebook**

## 📁 Project Structure

```text
customer-churn-ann/
│
├── Artificial_neural_network_churn_model.ipynb
├── Churn_Modelling.csv
└── README.md
```

> If the dataset is not included in the repository, make sure the CSV is available in the notebook's working directory before running the notebook.

## ▶️ How to Run

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd customer-churn-ann
```

### 2. Install dependencies

```bash
pip install tensorflow numpy pandas matplotlib scikit-learn jupyter
```

### 3. Launch the notebook

```bash
jupyter notebook
```

Open:

```text
Artificial_neural_network_churn_model.ipynb
```

Alternatively, the notebook can be opened directly in **Google Colab**.

### 4. Run the notebook

Execute the cells sequentially.

Make sure `Churn_Modelling.csv` is available at the path expected by the notebook:

```python
pd.read_csv('Churn_Modelling.csv')
```

## 🔍 Key Concepts Demonstrated

### Data Preprocessing
- Feature selection
- One-hot encoding
- Train-test split
- Standardization

### Deep Learning
- Artificial Neural Networks
- Dense layers
- ReLU activation
- Sigmoid activation
- Forward propagation
- Binary classification

### Model Training
- Adam optimizer
- Binary crossentropy
- Validation split
- Early stopping

### Evaluation
- Classification thresholding
- Confusion matrix
- Accuracy score
- Training/validation curves

## 🚀 Future Improvements

Possible improvements to make this project more production-oriented include:

- Add precision, recall, and F1-score
- Calculate ROC-AUC and plot the ROC curve
- Add a classification report
- Handle class imbalance explicitly
- Tune the ANN architecture and hyperparameters
- Compare ANN performance with Logistic Regression, Random Forest, and XGBoost
- Add model explainability using SHAP
- Save the trained model for inference
- Build a small web application for real-time churn prediction
- Add a reproducible requirements file

## 📌 Project Highlights

- Built an end-to-end ANN classification pipeline
- Performed categorical feature encoding and feature scaling
- Implemented Early Stopping to control training
- Achieved **85.55% test accuracy** on the provided dataset
- Evaluated predictions using a confusion matrix
- Visualized model training and validation behaviour

## 👩‍💻 Author

**Aradhana Behera**

This project was created as a hands-on implementation of Artificial Neural Networks and customer churn prediction.

---

⭐ If you find this project useful, consider giving the repository a star.
