# San Francisco Crime Classification & Clustering 🚔

This project applies Data Mining on the **San Francisco Crime Dataset** to detect high-crime areas and predict general crime types using **time** and **location** data.

It demonstrates the same pipeline in two ways:
1. **Code-first approach (Python)**
2. **Visual workflow (Orange Data Mining)**

---

## 📂 Project Structure

src/ → dmproject.py (Python code)
orange/ → DM_orange.ows (Orange workflow)
data/ → train.csv (dataset)
images/ → python_eda.png, orange_workflow.png

yaml
https://colab.research.google.com/drive/1qeaxl8mgzmvj9t__W1kt_EQhViCowid4?usp=sharing

Dataset source (Kaggle):  
https://www.kaggle.com/c/sf-crime/data

---

## 🛠️ Technologies Used

**Python**
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

**Orange Data Mining**
- Visual pipeline creation and model evaluation

---

## 🚀 Workflow Summary

### 1. Data Cleaning & Preprocessing
- Remove missing values
- Remove duplicates
- Convert `Dates` to datetime

**Python**:  
`dropna()`, `drop_duplicates()`, `pd.to_datetime()`

**Orange**:
- Select Rows
- Select Columns

---

### 2. Feature Engineering

Crime categories grouped into:

- **Violent** → ASSAULT, ROBBERY, BATTERY  
- **Property** → LARCENY/THEFT, BURGLARY, VEHICLE THEFT, TRESPASS  
- **Drug** → DRUG/NARCOTIC, DRUNKENNESS  

New features extracted:
- Hour
- DayOfWeek
- Month
- Encoded PdDistrict

Final features used:

Hour, DayOfWeek, Month, X, Y, PdDistrictEncoded

makefile
Copy code

Target:

CrimeGroupEncoded

yaml
Copy code

---

### 3. Clustering (Unsupervised Learning)

Goal: Find **hotspots**

**Python**
- K-Means (k = 5) on `X, Y, Hour`
- StandardScaler
- Silhouette Score for evaluation

**Orange**
- k-Means
- Scatter Plot
- Silhouette Plot

---

### 4. Classification (Supervised Learning)

Goal: Predict `CrimeGroup`

Models:
- Decision Tree (max_depth = 10)
- Random Forest (100 trees, balanced)

Evaluation:
- Accuracy
- Classification Report
- Confusion Matrix

---

## 📊 Visuals

**Python EDA**  
`images/python_eda.png`  
Distribution, hourly trends, districts, and spatial map

**Orange Workflow**  
`images/orange_workflow.png`  
Visual pipeline from data input to evaluation

---

## ▶️ How to Run

### Python

pip install pandas numpy matplotlib seaborn scikit-learn
python src/dmproject.py

makefile
Copy code

### Orange

Open:

orange/DM_orange.ows

yaml
Copy code

and run the workflow.

---

## ✅ Output

- Crime hotspot clusters
- Pattern analysis by time & location
- Model accuracy + classification report
- Confusion matrix
- Silhouette score

This shows a full data mining pipeline from raw data → patterns → prediction.
