
# 📈 Stock Price Prediction using LSTM

This project demonstrates how to build a **Stock Price Prediction Model** using a **Stacked LSTM (Long Short-Term Memory)** architecture in TensorFlow. It visualizes training/testing data performance and predicts future stock prices for the next 30 days.

## 🧰 Tech Stack
- Python
- Jupyter Notebook
- Libraries:
  - `pandas`, `numpy`
  - `matplotlib`
  - `scikit-learn`
  - `tensorflow`


## 📊 Dataset
- The model reads data from `stock.csv`, which include:
  - `Date` column (used for sorting)
  - `Close` column (used for training)
Make sure your `stock.csv` is in the same directory as the code file.


## 🔄 Workflow Overview

### 1. **Data Preprocessing** 🧹
- Handles missing values and sorts data by date.
- Extracted the `Close` price column for time series prediction.
- Scaled the values using `MinMaxScaler` to the range (0, 1).

### 2. **Data Visualization** 📊
- Initial data visualization is done using `matplotlib.pyplot` to view stock price trends.

### 3. **Sequence Preparation** 🧩
- Converts the closing price series into input/output pairs using a sliding window (`time_step=100`).

### 4. **Model Architecture** 🏗️
A Stacked LSTM with:
```python
LSTM(50, return_sequences=True)
LSTM(50, return_sequences=True)
LSTM(50)
Dense(1)
```

- Compiled with:
```python
loss='mean_squared_error'
optimizer='adam'
```

### 5. **Model Training** 🏋️
- `epochs=60`
- `batch_size=64`
- 10% of training data used as validation split

### 6. **Evaluation** ✅ 
- Uses **RMSE** (Root Mean Squared Error) for performance.
- Predictions are inverse transformed for interpretability.

### 7. **Visualization** 📈
- Compares predicted vs actual prices for training and testing sets.
- Plots continuous graph including the predicted next 30 days.

### 8. **Future Forecasting** 🔮
- Predicts closing prices for the **next 30 days** using the latest 100 days.



## 📈 Output Graphs
- Actual vs Predicted Prices (Train & Test)
- 30-Day Forecast
- Extended Line Plot with Predicted Future Data



## 🧪 How to Run

1. Make sure you have the dependencies installed:
```bash
pip install pandas numpy matplotlib scikit-learn tensorflow
```

2. Open the notebook:
```bash
jupyter notebook file.ipynb
```

3. Ensure `stock.csv` is present in the same directory.



## 📌 Notes
- This is a univariate time series prediction (based only on `Close` price).
- You can tweak `time_step`, number of epochs, and model architecture for better results or tuning.



## 📍 Directory Structure
```
.
├── file.ipynb
├── stock.csv
└── README.md
```



## 👩‍💻 About the Creator

This project was created by **Avneet Kaur**, a passionate developer and student specializing in Web Development, AI/ML, and Software Engineering.

- 💻 Experienced with: React.js, Python, Node.js, and more
- 🌱 Currently exploring: AI applications in real-world projects

Feel free to connect with me:
- 🌐 [Portfolio](https://avneet-kaur.framer.website)
- 💼 [LinkedIn](https://linkedin.com/in/avneet-kaur2)
