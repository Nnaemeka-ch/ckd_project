# Chronic Kidney Disease Prediction

Predicting whether a patient has **chronic kidney disease (CKD)** from routine clinical measurements, using **logistic regression**.

> 🚧 **Work in progress.** The notebook currently loads and explores the data. Data cleaning, model training and evaluation are being added step by step.

The planned model will take a patient's test results and health history, and output a **probability** that they have CKD (for example, 0.83 = 83% chance). The project was built to practise core machine learning ideas from the *Probability for AI* course (Stanford Online): maximum likelihood, gradient ascent, train/test splits, baselines, and spotting overfitting.

> ⚠️ **For educational purposes only.** This is not a medical tool and must not be used to diagnose or treat anyone.

---

## Data

**Source:** [Chronic Kidney Disease dataset](https://archive.ics.uci.edu/dataset/336), UCI Machine Learning Repository (dataset ID 336).

- **400 patients**, collected from a hospital over about 2 months
- **24 features** per patient, including:
  - **Demographics and vitals:** age, blood pressure
  - **Blood tests:** blood urea, serum creatinine, haemoglobin, sodium, potassium, white and red blood cell counts
  - **Urine tests:** specific gravity, albumin, sugar, pus cells, bacteria
  - **Medical history:** hypertension, diabetes, coronary artery disease, anaemia, appetite, pedal oedema
- **Target label:** `ckd` (chronic kidney disease) or `notckd`
- **Missing values:** present in several features, and will be handled before training

Donated by L. Rubini, P. Soundarapandian and P. Eswaran (2015).

---

## How to run it

### Requirements

- Python 3.10 or later
- Jupyter Notebook (or VS Code with the Jupyter extension)

### Installation

```bash
pip install ucimlrepo pandas scikit-learn
```

### Usage

1. Clone this repository:

   ```bash
   git clone https://github.com/Nnaemeka-ch/ckd_project.git
   cd ckd_project
   ```

2. Open `ckd_practice_1.ipynb` and run the cells in order.

The notebook loads the data directly from UCI:

```python
from ucimlrepo import fetch_ucirepo

chronic_kidney_disease = fetch_ucirepo(id=336)

X = chronic_kidney_disease.data.features   # inputs: 24 features
y = chronic_kidney_disease.data.targets    # label: ckd / notckd
```

---

## Limitations

- **Small dataset:** 400 patients is a small sample, so results may vary noticeably with different train/test splits.
- **Single source:** the data comes from one hospital, so the model may not work as well for patients from other hospitals or countries.
- **Missing values:** the method used to fill in missing measurements can affect the results.
- **Results can look too good:** many published models score very highly on this dataset. Strong test accuracy here does not show that the model would work in a real clinical setting.
- **Not clinically validated:** the model has not been reviewed or tested by medical professionals.

---

## Acknowledgements

- **Dataset:** L. Rubini, P. Soundarapandian and P. Eswaran, via the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/336). See the dataset page for its licence and citation details.
- **Course:** *Probability for AI*, Stanford Online.

## Licence

The code in this repository is available under the [MIT Licence](LICENSE). The dataset is subject to its own licence terms, set out on its UCI page.
