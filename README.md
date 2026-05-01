# 🚚 Food Delivery Time Prediction — End-to-End ML System

## 🚀 Overview

This project builds a **machine learning system to predict food delivery time** based on real-world operational factors such as distance, traffic, weather, and courier experience.

Unlike a basic ML model, this project implements a **complete production-style pipeline**:

> Data → Preprocessing → Model Training → Encoding → Model Serialization → Interactive UI

The system is deployed via a **Streamlit web application**, enabling real-time inference.

---

## 🎯 Problem Statement

Food delivery platforms must estimate delivery times accurately to:

* Improve customer satisfaction
* Optimize logistics and routing
* Reduce late deliveries
* Enhance operational efficiency

This project models delivery time as a function of **environmental, operational, and human factors**.

---

## 🧠 Key Idea

Delivery time is influenced by multiple variables:

```text
Delivery Time = f(Distance, Traffic, Weather, Time, Vehicle, Prep Time, Experience)
```

This system learns this relationship using a **Random Forest Regressor**, capturing non-linear dependencies in real-world data.

---

## 📊 Dataset

The dataset contains **1000 records** with features:

* Distance (km)
* Weather (Clear, Rainy, Foggy, etc.)
* Traffic Level (Low, Medium, High)
* Time of Day (Morning, Afternoon, Evening, Night)
* Vehicle Type (Bike, Scooter, Car)
* Preparation Time (minutes)
* Courier Experience (years)
* Target: Delivery Time (minutes)

### Data Challenges Handled

* Missing categorical values → filled using **mode**
* Missing numerical values → filled using **median**
* Irrelevant column removal (`Order_ID`) 

---

## 🏗️ System Architecture

```text
1. Data Layer:
    - Raw CSV dataset
    - Missing value handling
    - Feature selection

2. Processing Layer:
    - Label Encoding (categorical features)
    - Feature engineering

3. Model Layer:
    - Random Forest Regressor
    - Model optimization

4. Serialization Layer:
    - Trained model saved as .pkl
    - Encoders saved for inference consistency

5. Presentation Layer:
    - Streamlit UI for real-time predictions
```

---

## ⚙️ Tech Stack

* **Python**
* **Pandas / NumPy** → Data processing
* **Scikit-learn** → Model training
* **Random Forest** → Regression model
* **Pickle** → Model serialization
* **Streamlit** → Interactive web app

---

## 🤖 Model Details

### Algorithm: Random Forest Regressor

Why Random Forest?

* Captures non-linear relationships
* Robust to noise and outliers
* Works well with mixed feature types
* Reduces overfitting via ensemble learning

---

## 🔄 ML Pipeline

### 1. Data Cleaning

* Fill missing categorical values with mode
* Fill missing numerical values with median

### 2. Encoding

* Label Encoding for:

  * Weather
  * Traffic Level
  * Time of Day
  * Vehicle Type

### 3. Training

* Train Random Forest model on processed data
* Optimize parameters for better accuracy

### 4. Serialization

* Save trained model → `optimized_rf_model.pkl`
* Save encoders → `label_encoders.pkl`

### 5. Inference (App Layer)

* Load model + encoders
* Transform user inputs
* Predict delivery time in real-time

---

## 🌐 Streamlit Application

The app provides:

* User-friendly input interface
* Dropdowns for categorical features
* Real-time prediction output

### Example Flow

1. User enters:

   * Distance: 10 km
   * Traffic: High
   * Weather: Rainy

2. System:

   * Encodes inputs
   * Runs model

3. Output:

```text
Predicted Delivery Time: ~65 minutes
```

---

## 📈 Key Insights

* Distance and traffic are the strongest predictors
* Weather conditions significantly impact delivery time
* Courier experience reduces variability
* Non-linear models outperform linear baselines

---

## 🚀 How to Run

```bash
# Install dependencies
pip install -r requirements.txt

# Run the app
streamlit run app.py
```

---

## 📌 Limitations

* Uses Label Encoding (may introduce ordinal bias)
* Dataset size is relatively small (1000 rows)
* No real-time traffic API integration

---

## 🔥 Future Improvements

* Replace Label Encoding with One-Hot Encoding
* Use advanced models (XGBoost, LightGBM)
* Add real-time data integration (Google Maps API)
* Deploy using Docker + Cloud (AWS/GCP)
* Build REST API using FastAPI
* Add model monitoring & logging

---

## 🧠 Engineering Takeaways

This project demonstrates:

* End-to-end ML pipeline design
* Handling real-world noisy data
* Model deployment via UI
* Consistent preprocessing between training and inference
* Practical application of ensemble learning

---

## ⭐ Why This Project Matters

This system reflects how real-world delivery platforms estimate ETAs:

> Data-driven decision systems powering logistics at scale

It bridges the gap between:

* Academic ML models
* Production-ready systems

---

## 🤝 Contribution

Contributions welcome for:

* Model improvements
* Feature engineering
* Deployment enhancements

---

## 📄 License

MIT License
