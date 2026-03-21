---

# 📊 Notebook 1: Data Preprocessing

## 📂 File
`notebooks/01_data_preprocessing.ipynb`

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

---

### 2. Data Exploration
- Checked dataset structure using `info()`
- Generated statistical summary using `describe()`
- Identified missing values

---

### 3. Data Cleaning
- Handled missing values:
  - Numerical → Mean
  - Categorical → Mode
- Ensured dataset consistency

---

### 4. Feature Engineering
- Converted `timestamp` to datetime format
- Extracted:
  - Hour
  - Day
  - Month
- Created time-based features for analysis

---

### 5. Data Visualization
- Hourly energy consumption trends
- Appliance-wise energy usage
- Correlation heatmap for feature relationships

---

### 6. Data Normalization
- Applied MinMaxScaler
- Scaled features between 0 and 1
- Prepared data for deep learning models

---

### 7. Sequence Creation (LSTM Preparation)

- Created time-series sequences using sliding window
- Sequence length: 24 (past 24 hours)
- Generated:
  - `X` → input sequences
  - `y` → target values

---

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

## 🚀 Next Step

👉 Notebook 2: LSTM Model Training  

- Train deep learning model  
- Evaluate performance  
- Generate predictions  

---

---

# 🤖 Notebook 2: LSTM Model Training

## 📂 File
`notebooks/02_lstm_training.ipynb`

---

## 🚀 Overview

This notebook focuses on building and training a **Deep Learning model (LSTM)** to predict electricity consumption using time-series data.

The model learns patterns from historical energy usage and predicts future consumption.

---

## 📊 Input Data

The model uses preprocessed data generated from Notebook 1:

- `X.npy` → Input sequences (time-series data)
- `y.npy` → Target values (energy consumption)
- `scaler.pkl` → Data normalization model

---

## ⚙️ Steps Performed

### 1. Data Loading
- Uploaded processed `.npy` files and scaler
- Loaded input sequences and target values

### 2. Train-Test Split
- 80% training data  
- 20% testing data  

---

### 3. Model Architecture

The LSTM model consists of:

- LSTM Layer (64 units)
- Dropout (0.2)
- LSTM Layer (64 units)
- Dropout (0.2)
- Dense Layer (ReLU)
- Output Layer (1 neuron)

---

### 4. Model Training

- Loss Function: Mean Squared Error (MSE)
- Optimizer: Adam
- Epochs: 20
- Batch Size: 32
- Early Stopping used to prevent overfitting

---

### 5. Model Evaluation

Performance metrics used:

- MAE (Mean Absolute Error)
- RMSE (Root Mean Square Error)
- R² Score

---

### 6. Visualization

- Training vs Validation Loss
- Actual vs Predicted Energy Consumption

---

### 7. Model Saving

The trained model is saved as:
models/lstm_model.h5


---

## 📈 Output

- Accurate prediction of electricity consumption
- Graphs for performance analysis
- Trained deep learning model ready for deployment

---

## 🎯 Key Achievements

✔ Successfully trained LSTM model  
✔ Captured time-series patterns  
✔ Achieved reliable prediction accuracy  
✔ Model ready for real-world usage  

---

## 🚀 Next Step

👉 Notebook 3: Model Evaluation & API Development  
👉 Deploy model using Flask / FastAPI  
👉 Build dashboard for visualization  

---