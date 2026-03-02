❤️ **Framingham Heart Study - Heart Disease Prediction**

Project overview:
This project builds and evaluates multiple machine learning models to predict the 10-year risk of heart disease using the **Framingham Heart Study** dataset.
**Goal:** Predict `TenYearCHD` based on patient features.
**Dataset source:** Kaggle - `noeyislearning/framingham-heart-study`

Dataset description:
The dataset contains 15 patient features:

* `male`: Gender (1=male, 0=female)
* `age`: Age in years
* `education`: Education level (1-4)
* `currentSmoker`: Current smoker (1=yes, 0=no)
* `cigsPerDay`: Average cigarettes per day
* `BPMeds`: Blood pressure medication (1=yes, 0=no)
* `prevalentStroke`: History of stroke (1=yes, 0=no)
* `prevalentHyp`: Hypertension (1=yes, 0=no)
* `diabetes`: Diabetes (1=yes, 0=no)
* `totChol`: Total cholesterol
* `sysBP`: Systolic blood pressure
* `diaBP`: Diastolic blood pressure
* `BMI`: Body Mass Index
* `heartRate`: Heart rate per minute
* `glucose`: Blood glucose level

Data preprocessing:

1. Split data 80/20 stratified to maintain class balance.
2. Scale numeric features using `MinMaxScaler`.
3. Impute missing values with median using `SimpleImputer`.

Models used:

* Logistic Regression
* Random Forest
* XGBoost
* SVM
* Decision Tree
* KNN
* Gradient Boosting
* AdaBoost
* Naive Bayes
* MLP Neural Network

Evaluation:

* Each model is trained on the training set and evaluated on the test set.
* Accuracy is measured and sorted to select the top-performing models.

Model saving:

* Top 9 models saved as `.pkl` files
* Preprocessing objects saved:

  * `scaler.pkl`
  * `imputer.pkl`

Inference on new data:
Steps:

1. Load `scaler.pkl` and `imputer.pkl`
2. Transform new data: scale → impute
3. Load model `.pkl`
4. Predict `TenYearCHD` risk

Example:

```
data_new_scaled = scaler.transform(data_new)
data_new_clean = imputer.transform(data_new_scaled)
loaded_model = joblib.load('Random_Forest.pkl')
prediction = loaded_model.predict(data_new_clean)
print(prediction)
```

Key features:

* Multi-model comparison for best accuracy
* Automatic handling of missing values & scaling
* Easy to extend with new models
* Ready for predicting new patient data

Requirements:

```
pip install pandas scikit-learn xgboost joblib kagglehub
```

References:

* Framingham Heart Study Dataset - Kaggle
* Scikit-learn documentation
* XGBoost documentation

---

Author: Muhammad Auffa Hakim Aditya

