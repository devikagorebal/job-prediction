# About my first project on github
#🎯 Job Role Prediction using Machine Learning & Django

A complete beginner-friendly web app that predicts a candidate's job role
using 6 ML algorithms, built with Python, Scikit-learn, and Django.

---

## 📁 Project Folder Structure

```
job_role_project/
│
├── manage.py                        ← Django's main control file
│
├── job_role_project/                ← Django project settings
│   ├── settings.py                  ← All project settings
│   └── urls.py                      ← Main URL routing
│
├── predictor/                       ← Our Django app
│   ├── views.py                     ← All logic (login, predict, etc.)
│   ├── urls.py                      ← App URL routing
│   ├── models.py                    ← Database models
│   └── templates/predictor/
│       ├── base.html                ← Base layout (navbar, etc.)
│       ├── login.html               ← Login page
│       ├── register.html            ← Register page
│       └── predict.html             ← Main prediction page
│
└── ml_model/                        ← Machine Learning files
    ├── job_role_dataset.csv         ← Training dataset
    ├── train_models.py              ← Script to train & save models
    ├── models.pkl                   ← Saved ML models (auto-generated)
    ├── encoders.pkl                 ← Saved label encoders (auto-generated)
    ├── scaler.pkl                   ← Saved scaler (auto-generated)
    └── accuracies.pkl               ← Saved accuracies (auto-generated)
```

---

## 🚀 HOW TO RUN (Step by Step for Beginners)

### Step 1 — Install Python
Download Python 3.10+ from: https://www.python.org/downloads/
✅ During install, check "Add Python to PATH"

### Step 2 — Open Terminal / Command Prompt
- Windows: Press Win + R, type `cmd`, press Enter
- Mac/Linux: Open Terminal

### Step 3 — Navigate to the project folder
```
cd path/to/job_role_project
```
Example: `cd C:\Users\YourName\Downloads\job_role_project`

### Step 4 — Install required Python libraries
```
pip install django scikit-learn pandas numpy
```
Wait for it to finish (may take 1–2 minutes).

### Step 5 — Train the ML Models (do this ONCE)
```
cd ml_model
python train_models.py
cd ..
```
This creates the .pkl files (saved models). You'll see accuracy for each algorithm.

### Step 6 — Set up the Django database
```
python manage.py migrate
```

### Step 7 — Run the web server
```
python manage.py runserver
```
You'll see: `Starting development server at http://127.0.0.1:8000/`

### Step 8 — Open your browser
Go to: http://127.0.0.1:8000/

---

## 🧠 How the ML Part Works (Beginner Explanation)

1. **Dataset** (job_role_dataset.csv)
   - Contains 107 candidate profiles
   - Features: Age, Gender, Degree, Field, Experience, Certifications, Skills, Location
   - Target: Job Role (Software Developer, Data Scientist, etc.)

2. **Preprocessing**
   - Categorical columns (like "Male/Female") are converted to numbers
   - All features are scaled to the same range (StandardScaler)

3. **6 ML Algorithms Used**
   | Algorithm | How it works (simple) |
   |---|---|
   | Logistic Regression | Draws a line to separate classes |
   | Decision Tree | Makes decisions using if-else rules |
   | Random Forest | Uses many decision trees, votes on result |
   | SVM | Finds the best boundary between classes |
   | KNN | Looks at K nearest similar people, votes |
   | Naive Bayes | Uses probability theory |

4. **Prediction**
   - User enters candidate details on the website
   - All 6 models predict the job role
   - Results are shown with accuracy comparison

---

## 🌐 Pages in the Web App

| URL | Page |
|---|---|
| /register/ | Create new account |
| /login/ | Log in |
| /predict/ | Enter details & predict job role |
| /logout/ | Log out |

---

## 📊 Features

✅ User Registration & Login (with session management)
✅ Prediction form with all 8 input fields
✅ 6 ML models run simultaneously
✅ Results table with accuracy comparison
✅ Best performing algorithm highlighted
✅ Visual accuracy bar chart in the table
✅ Responsive design (works on mobile too)

---

## ❓ Troubleshooting

**"No module named django"** → Run: `pip install django`
**"No module named sklearn"** → Run: `pip install scikit-learn`
**"models.pkl not found"** → You forgot Step 5. Run `python ml_model/train_models.py`
**Port already in use** → Run: `python manage.py runserver 8080` and go to http://127.0.0.1:8080/
