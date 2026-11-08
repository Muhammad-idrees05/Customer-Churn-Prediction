# 📊 Customer Churn Prediction Using Artificial Neural Networks (ANN)

## 📌 Project Overview

This project uses Deep Learning to predict customer churn in the banking sector. It implements an **Artificial Neural Network (ANN)** using TensorFlow and Keras to identify customers who are likely to leave the bank.

The model processes customer demographic, financial, and behavioral information, applies categorical encoding and feature scaling, and learns patterns associated with customer churn.

The project also includes dropout regularization, early stopping, training-history visualization, and prediction on unseen customer records.

## 🎯 Project Objectives

- Analyze customer information and identify churn-related patterns.
- Preprocess numerical and categorical features.
- Apply One-Hot Encoding to categorical variables.
- Standardize numerical input features.
- Build and train a deep Artificial Neural Network.
- Reduce overfitting using Dropout layers and Early Stopping.
- Evaluate model performance using classification metrics.
- Predict churn probabilities for unseen customers.

## 📂 Dataset

**Dataset:** `Churn_Modelling.csv`

The dataset contains customer information, including demographic, financial, and account-related attributes.

### Target Variable

`Exited`

- `0` – Customer stays with the bank.
- `1` – Customer leaves the bank.

### Data Cleaning

The following unnecessary columns are removed:

- `RowNumber`
- `CustomerId`
- `Surname`

These columns are excluded from model training.

## 🛠️ Technologies and Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- TensorFlow
- Keras

## ⚙️ Data Preprocessing

### 1. Categorical Encoding

One-Hot Encoding is applied to:

- `Geography`
- `Gender`

This converts categorical information into numerical features suitable for neural network training.

### 2. Feature Scaling

`StandardScaler` is used to standardize the input features before training.

### 3. Train-Test Split

The dataset is divided into:

- Training data: 80%
- Testing data: 20%
- Random state: 42

## 🧠 Artificial Neural Network Architecture

The project uses a fully connected Artificial Neural Network built with TensorFlow and Keras.

### Model Architecture

| Layer | Neurons | Activation |
|---|---:|---|
| Input Dense | 512 | ReLU |
| Dropout | 30% | — |
| Dense | 256 | ReLU |
| Dropout | 30% | — |
| Dense | 128 | ReLU |
| Dropout | 20% | — |
| Dense | 64 | ReLU |
| Dropout | 20% | — |
| Dense | 28 | ReLU |
| Dense | 10 | ReLU |
| Output Dense | 1 | Sigmoid |

### Model Configuration

- Optimizer: Adam
- Loss Function: Binary Crossentropy
- Evaluation Metric: Accuracy
- Batch Size: 32
- Maximum Epochs: 20
- Early Stopping: Enabled
- Early Stopping Monitor: `val_loss`
- Patience: 5
- Restore Best Weights: True

## 🛡️ Overfitting Prevention

Two techniques are implemented:

**Dropout Regularization:** Randomly disables a percentage of neurons during training to reduce dependence on individual neurons.

**Early Stopping:** Monitors validation loss and stops training when the model stops improving for five consecutive epochs. The best weights are restored.

## 📈 Training Visualization

The project visualizes the training process using Matplotlib.

Included plots:

1. Training Accuracy vs Validation Accuracy.
2. Training Loss vs Validation Loss.

These visualizations help monitor model learning and identify possible overfitting.

## 📊 Model Evaluation

The model is evaluated using:

- **Confusion Matrix:** Shows correct and incorrect churn predictions.
- **Classification Report:** Provides precision, recall, and F1-score.
- **Accuracy Score:** Measures overall prediction accuracy.

### Classification Threshold

The model uses a prediction threshold of `0.3`:

- Probability greater than 0.3 → Customer likely to leave.
- Probability less than or equal to 0.3 → Customer likely to stay.

The threshold is configurable and affects the balance between precision and recall.

## 🔮 Prediction on Unseen Data

The project demonstrates churn prediction using three unseen customer records.

The ANN generates churn probabilities, which are converted into binary predictions using the 0.3 threshold.

This demonstrates how the trained model can classify new customer records.

## 🚀 Installation and Usage

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/customer-churn-prediction.git
```

### 2. Navigate to the Project Directory

```bash
cd customer-churn-prediction
```

### 3. Install Dependencies

```bash
pip install pandas numpy matplotlib scikit-learn tensorflow
```

### 4. Run the Notebook

```bash
jupyter notebook
```

Open the notebook and execute the cells to preprocess the dataset, train the ANN, visualize performance, and generate predictions.

## 📁 Project Structure

```text
Customer-Churn-Prediction/
│
├── Churn_Modelling.csv
├── Customer_Churn_Prediction.ipynb
├── README.md
│
└── requirements.txt
```

## 🔧 Future Improvements

- Use a preprocessing pipeline to prevent data leakage.
- Apply stratified train-test splitting.
- Tune the classification threshold using validation data.
- Compare ANN performance with Random Forest, XGBoost, and other classifiers.
- Add ROC-AUC and Precision-Recall curves.
- Build an interactive Streamlit application.
- Save the trained ANN model and preprocessing objects for deployment.

## 👨‍💻 Author

**Muhammad Idrees**  
AI & Machine Learning Developer

Interested in Machine Learning, Deep Learning, Computer Vision, NLP, and AI-powered applications.

⭐ If you find this project useful, consider giving the repository a star!
