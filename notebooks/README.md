---

# 📊 Notebook 1: Data Preprocessing

---

## 🚀 Overview

This notebook performs **data preprocessing and feature engineering** on the electricity consumption dataset.

It prepares the raw data into a clean and structured format suitable for training machine learning and deep learning models.

---

## 📊 Input Data

- Raw electricity dataset (CSV file uploaded in Google Colab)
- Contains:
  - Energy consumption (kWh)
  - Power usage (Watts)
  - Temperature settings
  - Appliance usage
  - Time-based features
  - Carbon emissions and cost

---

## ⚙️ Steps Performed

### 1. Data Loading
- Uploaded dataset using Google Colab
- Loaded into Pandas DataFrame

### 2. Data Exploration
- Checked dataset structure using `info()`
- Generated statistical summary using `describe()`
- Identified missing values

### 3. Data Cleaning
- Handled missing values:
  - Numerical → Mean
  - Categorical → Mode
- Ensured dataset consistency

### 4. Feature Engineering
- Converted `timestamp` to datetime format
- Extracted:
  - Hour
  - Day
  - Month

### 5. Data Visualization
- Hourly energy consumption trends
- Appliance-wise energy usage
- Correlation heatmap

### 6. Data Normalization
- Applied MinMaxScaler
- Scaled features between 0 and 1

### 7. Sequence Creation (LSTM Preparation)
- Created time-series sequences using sliding window
- Sequence length: 24 (past 24 hours)
- Generated:
  - `X` → input sequences
  - `y` → target values

### 8. Data Saving

Processed data saved as:


models/scaler.pkl
data/processed/X.npy
data/processed/y.npy


---

## 📈 Output

- Clean and structured dataset  
- Normalized feature values  
- LSTM-ready sequences  
- Saved preprocessing artifacts  

---

## 🎯 Key Achievements

✔ Handled missing data effectively  
✔ Created meaningful time-based features  
✔ Prepared dataset for time-series modeling  
✔ Generated sequences for LSTM training  

---

# 🤖 Notebook 2: LSTM Model Training

---

## 🚀 Overview

This notebook builds and trains a **Deep Learning LSTM model** to predict electricity consumption using time-series data.

---

## 📊 Input Data

- `X.npy` → Input sequences  
- `y.npy` → Target values  
- `scaler.pkl` → Data normalization  

---

## ⚙️ Steps Performed

### 1. Data Loading
- Uploaded processed files
- Loaded sequences and targets

### 2. Train-Test Split
- 80% training data  
- 20% testing data  

### 3. Model Architecture

- LSTM Layer (64 units)
- Dropout (0.2)
- LSTM Layer (64 units)
- Dropout (0.2)
- Dense Layer (ReLU)
- Output Layer (1 neuron)

### 4. Model Training

- Loss Function: MSE  
- Optimizer: Adam  
- Epochs: 20  
- Batch Size: 32  
- EarlyStopping used  

### 5. Model Evaluation

- MAE (Mean Absolute Error)  
- RMSE (Root Mean Square Error)  
- R² Score  

### 6. Visualization

- Training vs Validation Loss  
- Actual vs Predicted Graph  

### 7. Model Saving

Model saved as:


models/lstm_model.h5


---

## 📈 Output

- Energy consumption predictions  
- Performance graphs  
- Trained deep learning model  

---

## 🎯 Key Achievements

✔ Built LSTM model  
✔ Learned time-series patterns  
✔ Achieved good prediction accuracy  
✔ Model ready for deployment  

---

## 🚀 Next Step

👉 Notebook 3: Model Evaluation & API Development  
👉 Flask / FastAPI deployment  
👉 Dashboard visualization  

---