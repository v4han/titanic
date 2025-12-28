# Titanic Survival Prediction

[Kaggle Competition Link](https://www.kaggle.com/competitions/titanic/data)

This project contains a Python-based solution for the Titanic survival prediction challenge. It uses a combination of two machine learning models to predict which passengers survived the disaster based on features like age, class, and family size.

## 📊 Dataset & Setup

To run this code, you will need the following files from the [Kaggle Titanic page](https://www.kaggle.com/competitions/titanic/data) in your root folder:

* `train.csv`
* `test.csv`
* `gender_submission.csv` (template for final output)
* `titanic.ipynb` (the main code file)

---

## 🛠️ Data Processing

The code cleans the data and creates several new features to help the model identify patterns:

### 1. New Binary Features

* **Has_Cabin:** A simple 1/0 column to show if a cabin number was listed for the passenger.
* **IsAlone:** A column indicating if the passenger was traveling without any family members (based on siblings, spouses, parents, or children).

### 2. Titles and Age Groups

Instead of using raw data, the information was organized into specific categories:

* **Title Extraction:** Used Regex to extract the most common titles: **Mr, Miss, Mrs, and Master**.
* **Age Categorization:** Passengers were sorted into specific groups rather than using exact ages:
* `Child` (0–12)
* `Adolescent` (13–19)
* `Young Adult` (20–40)
* `Adult` (41–60)
* `Senior` (60+)



---

## 🤖 Modeling

The solution uses a **Soft Voting Classifier**, which is an ensemble method that combines the predictions of two models:

1. **Random Forest (RF)**
2. **XGBoost**

The categorical data (Sex, Embarked, Title, and Age_Group) was processed using **Label Encoding** so it could be read by these models.

---

## 🚀 How to Run

1. Clone the repository.
2. Install the requirements:
```bash
pip install -r requirements.txt

```


3. Run the notebook.

**Current Accuracy: ~78%**
