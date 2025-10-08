🫁 Lung Cancer Prediction using Support Vector Machine (SVM)

📘 Overview

This project aims to predict the likelihood of lung cancer based on patient lifestyle and medical attributes using a Support Vector Machine (SVM) model. The dataset includes multiple factors such as smoking habits, fatigue, anxiety, chronic disease, and more.

📂 Dataset Information

The dataset used is survey lung cancer.csv, which contains 309 samples and 16 columns.
Each record represents a patient with several health and lifestyle features.

🧾 Columns:

GENDER 🧍‍♂️🧍‍♀️

AGE 🎂

SMOKING 🚬

YELLOW_FINGERS 💛

ANXIETY 😰

PEER_PRESSURE 👥

CHRONIC DISEASE 🧬

FATIGUE 😴

ALLERGY 🤧

WHEEZING 😮‍💨

ALCOHOL CONSUMING 🍷

COUGHING 🤧

SHORTNESS OF BREATH 🫤

SWALLOWING DIFFICULTY 😣

CHEST PAIN ❤️‍🔥

LUNG_CANCER 🎯 (Target Variable)

⚙️ Steps Involved
1️⃣ Data Loading
import pandas as pd
df = pd.read_csv('survey lung cancer.csv')

2️⃣ Data Exploration

Checked for null values

Displayed dataset info and description

Visualized data using seaborn and matplotlib

3️⃣ Label Encoding

Categorical variables like GENDER and LUNG_CANCER were converted to numerical form using:

from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
df['GENDER'] = le.fit_transform(df['GENDER'])
df['LUNG_CANCER'] = le.fit_transform(df['LUNG_CANCER'])

4️⃣ Train-Test Split
from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test = train_test_split(x, y, test_size=0.2, random_state=42)

5️⃣ Feature Scaling
from sklearn.preprocessing import StandardScaler
sc = StandardScaler()
x_train = sc.fit_transform(x_train)
x_test = sc.transform(x_test)

6️⃣ Model Training (SVM)
from sklearn.svm import SVC
model = SVC()
model.fit(x_train, y_train)

7️⃣ Model Evaluation
model.score(x_train, y_train)*100, model.score(x_test, y_test)*100


✅ Training Accuracy: ~94.7%
✅ Testing Accuracy: ~93.5%

🔢 Confusion Matrix
from sklearn.metrics import confusion_matrix
cm = confusion_matrix(y_test, y_pred)
print(cm)

📊 Visualizations

The project includes:

Histograms for age and cancer distribution

Bar plots for categorical feature analysis

Heatmap for correlation matrix

💡 Insights

Most patients in the dataset are older adults (50–80 years).

Smoking, anxiety, and fatigue show strong correlations with lung cancer.

The SVM model performs exceptionally well with minimal overfitting.

🧠 Technologies Used

Python 🐍

Pandas, NumPy

Matplotlib, Seaborn

Scikit-learn

🚀 How to Run

Clone this repository or upload the notebook to Google Colab.

Upload the dataset survey lung cancer.csv.

Run all cells sequentially.

View the output metrics and visualizations.

🏁 Results Summary
Metric	Training	Testing
Accuracy	94.73%	93.55%
🧩 Future Improvements

Experiment with other models like Random Forest or Logistic Regression.

Apply hyperparameter tuning for better accuracy.

Add ROC-AUC and precision-recall metrics for deeper evaluation.

👨‍💻 Author

Project by: PRIYA KUMARI
📅 DATE :- 08/10/2025
🔗 Built and tested on Google Colab
