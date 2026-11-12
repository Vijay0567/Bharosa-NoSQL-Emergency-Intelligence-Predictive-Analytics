# 🛡️ Bharosa: NoSQL-Based Emergency Intelligence and Predictive Analytics Platform

Bharosa is a NoSQL-based Emergency Intelligence and Predictive Analytics Platform developed to analyze emergency event data and identify potential emergency situations using Machine Learning.

The project integrates **MongoDB** as its NoSQL database, **PyMongo** for database operations, and **Python** for data processing and machine learning. It uses Logistic Regression and Random Forest classification algorithms to predict emergency situations based on factors such as travel speed, time of day, location risk score, and previous SOS events.

An interactive **Streamlit dashboard** provides analytical insights into emergency events, dataset distribution, and machine learning model performance through visualizations and evaluation metrics.

## 🎯 Project Objectives

- Develop a NoSQL-based system for storing and managing emergency event data.
- Implement MongoDB CRUD operations using PyMongo.
- Perform data cleaning, validation, and preprocessing.
- Analyze emergency patterns using data analytics.
- Predict emergency situations using Machine Learning algorithms.
- Compare classification models using standard evaluation metrics.
- Present analytical insights through an interactive dashboard.

## 🚀 Key Features

- **NoSQL Database Integration:** Uses MongoDB to store and manage structured emergency event records in JSON-like BSON documents.
- **CRUD Operations:** Implements Create, Read, Update, and Delete operations using PyMongo.
- **Dataset Generation:** Generates 3,000 synthetic emergency event records containing GPS coordinates, timestamps, travel speed, location risk scores, and SOS history.
- **Data Preprocessing:** Handles duplicate records, missing values, data type conversion, and invalid data validation.
- **Emergency Classification:** Predicts whether an event is Normal or Emergency.
- **Machine Learning Models:** Implements Logistic Regression and Random Forest classifiers.
- **Model Evaluation:** Evaluates models using Accuracy, Precision, Recall, F1-Score, and Confusion Matrix.
- **Data Visualization:** Generates charts for emergency distribution, speed versus location risk, and model performance.
- **Interactive Dashboard:** Uses Streamlit and Plotly to display emergency analytics and predictive insights.

## 🛠️ Technology Stack

| Category | Technologies |
|---|---|
| Programming Language | Python |
| NoSQL Database | MongoDB |
| Database Connectivity | PyMongo |
| Data Processing | Pandas, NumPy |
| Machine Learning | Scikit-learn |
| Classification Algorithms | Logistic Regression, Random Forest |
| Data Visualization | Matplotlib, Seaborn, Plotly |
| Dashboard | Streamlit |
| Data Format | JSON |

## 📊 NoSQL Database Implementation

Bharosa uses MongoDB as its primary NoSQL database to store emergency event records.

**Database:** `bharosa_db`

**Collection:** `bharosa_events_v2`

Each document contains information such as:

- Event ID
- Timestamp
- Latitude and Longitude
- Travel Speed (km/h)
- Time of Day
- Location Risk Score
- Previous SOS Count
- Emergency Status
- Response Time (minutes)

### CRUD Operations

The project implements all four fundamental MongoDB operations using PyMongo:

1. **Create:** Insert new emergency event documents.
2. **Read:** Retrieve emergency records using queries.
3. **Update:** Modify existing event information.
4. **Delete:** Remove selected emergency records.

These operations demonstrate practical NoSQL database management and document-based data handling.

## 🤖 Machine Learning Approach

Bharosa implements two supervised classification algorithms to identify potential emergency situations.

### 1. Logistic Regression

Used as a classification model to estimate the probability of an emergency event based on the selected input features.

### 2. Random Forest Classifier

Uses an ensemble of decision trees to classify emergency events and capture relationships between multiple risk factors.

### Input Features

- `speed_kmh`
- `time_of_day`
- `location_risk_score`
- `previous_sos_count`

**Target Variable:** `emergency_status`

The target variable contains two classes:

- Normal
- Emergency

### Model Training

- Dataset: 3,000 synthetic records.
- Training Data: 80%.
- Testing Data: 20%.
- Train-test split uses stratified sampling.
- Random State: 42.

### Evaluation Metrics

The models are evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix

The results are stored in JSON and CSV files for model comparison and further analysis.

## 🔄 Project Workflow

1. Generate synthetic emergency event data using Python.
2. Store the generated records in MongoDB.
3. Perform CRUD operations using PyMongo.
4. Retrieve records from MongoDB for preprocessing.
5. Clean and validate the emergency dataset.
6. Train Logistic Regression and Random Forest models.
7. Evaluate model performance using classification metrics.
8. Save trained models using Joblib.
9. Generate analytical visualizations.
10. Present results through an interactive Streamlit dashboard.

## 📁 Project Structure

```text
Bharosa/
│
├── dashboard/
│   └── app.py
│
├── database/
│   ├── mongodb_connection.py
│   ├── import_dataset.py
│   └── crud_operations.py
│
├── dataset/
│   ├── generate_dataset.py
│   ├── bharosa_dataset.json
│   └── bharosa_cleaned.json
│
├── preprocessing/
│   └── preprocess_data.py
│
├── machine_learning/
│   ├── train_models.py
│   └── saved_models/
│       ├── logistic_regression.pkl
│       └── random_forest.pkl
│
├── visualizations/
│   └── generate_visualizations.py
│
├── results/
│   ├── bharosa_cleaned.csv
│   ├── model_comparison.csv
│   ├── model_results.json
│   ├── event_distribution.png
│   ├── model_comparison.png
│   ├── speed_vs_risk.png
│   ├── logistic_confusion_matrix.png
│   └── random_forest_confusion_matrix.png
│
├── requirements.txt
└── README.md
```

## ⚙️ Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/Bharosa.git
cd Bharosa
```

### 2. Create a Virtual Environment

```bash
python -m venv .venv
```

### 3. Activate the Environment

Windows:

```bash
.venv\Scripts\activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Start MongoDB

Make sure MongoDB Community Server is installed and running locally.

The project uses the following MongoDB connection:

```python
mongodb://localhost:27017/
```

### 6. Generate the Dataset

```bash
python dataset/generate_dataset.py
```

### 7. Import Data into MongoDB

```bash
python database/import_dataset.py
```

### 8. Execute CRUD Operations

```bash
python database/crud_operations.py
```

### 9. Perform Data Preprocessing

```bash
python preprocessing/preprocess_data.py
```

### 10. Train Machine Learning Models

```bash
python machine_learning/train_models.py
```

### 11. Generate Visualizations

```bash
python visualizations/generate_visualizations.py
```

### 12. Launch the Streamlit Dashboard

```bash
streamlit run dashboard/app.py
```

## 📈 Expected Outcomes

Bharosa demonstrates how NoSQL databases, data preprocessing, and machine learning can be integrated into an emergency analytics platform.

The system provides:

- Centralized storage of emergency event records.
- Efficient document-based database operations.
- Identification of patterns in emergency-related data.
- Predictive classification of normal and emergency events.
- Comparative evaluation of machine learning algorithms.
- Interactive visual insights for understanding emergency data.

## 📚 Dataset Information

The project uses a **synthetically generated dataset of 3,000 records** created using Python and NumPy because real-world emergency records were not available.

The dataset simulates emergency-related information, including GPS coordinates around Hyderabad, timestamps, travel speeds, location risk scores, previous SOS counts, emergency classifications, and simulated response times.

The dataset is intended for academic experimentation and demonstrating NoSQL database operations, data analytics, and machine learning techniques. It does not represent real emergency incidents or validated real-world risk predictions.

## 🔮 Future Enhancements

- Integrate real-time GPS tracking and emergency alerts.
- Connect the platform with live location services.
- Implement geospatial queries using MongoDB.
- Introduce real-world emergency datasets for model validation.
- Develop real-time emergency monitoring and notification features.
- Enhance predictive performance using additional relevant features.

## 👨‍💻 Author

**Gampala Vijay Kumar**

B.Tech Computer Science and Engineering

Lovely Professional University

GitHub: https://github.com/Vijay0567

---

*Bharosa demonstrates the practical application of NoSQL database management, Python-based data analytics, and Machine Learning for emergency intelligence and predictive analysis.*
