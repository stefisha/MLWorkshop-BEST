# Introduction to AI and Machine Learning

**BEST Belgrade · October to November 2022**

Workshop facilitator: [Stefan Veličković](https://github.com/stefisha)

An internal workshop series for BEST Belgrade students taking their first steps
into artificial intelligence. The sessions combined an introduction to machine
learning with a practical classification exercise in Google Colab.

## Workshop series

| Session | Focus | Status |
| --- | --- | --- |
| Introduction to AI | Core concepts and machine learning fundamentals | Delivered |
| Practical machine learning | Traditional classification models and evaluation in Python | Delivered |
| Neural networks | A planned continuation of the introductory series | Planned, not delivered |

I organized and facilitated the sessions, introducing the concepts first and then
guiding participants through a customer churn classification task. The goal was
to make the connection between the ideas and a working machine learning workflow.

## Materials

* [Introductory slides](AI%20bootcamp%20V3.pptx)
* [Practical notebook](Notebook_Klasifikacija_Radionica.ipynb), with explanations and discussion prompts in Serbian
* [Customer churn dataset](Data/churn.csv), included for the practical exercise
* [Additional exercises](Extra/), archived datasets for heart disease classification and price prediction

The additional datasets are practice resources, not completed workshop solutions.
The neural networks session is not included in this repository.

## Practical session

Participants work through a telecom customer churn example using pandas, NumPy,
scikit learn, and Yellowbrick. The notebook introduces:

1. Features, targets, and numerical feature selection
2. Decision trees, naive Bayes, nearest neighbors, and logistic regression
3. Training scores, a separate test set, and cross validation
4. Learning curves and the majority class baseline
5. Confusion matrices, precision, recall, F1, and the cost of errors

The final section contains commented examples for decision thresholds, ROC curves,
and AUC, intended for further exploration.

This is a teaching notebook. Some examples deliberately evaluate on the training
set before introducing held out evaluation. Those scores illustrate the concepts
and should not be interpreted as evidence of performance on new customers.

## Open in Google Colab

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/stefisha/MLWorkshop-BEST/blob/main/Notebook_Klasifikacija_Radionica.ipynb)

The loading cell uses the included CSV when running locally and the same file
from this repository when running in Colab. Install the notebook dependencies in
a Colab cell if they are missing:

```python
%pip install pandas numpy scikit-learn matplotlib yellowbrick
```

Run the notebook cells in order. No GPU or API keys are required.

## Run locally

Use Python 3.9 to 3.12 and open Jupyter from the repository root:

```sh
git clone https://github.com/stefisha/MLWorkshop-BEST.git
cd MLWorkshop-BEST
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt jupyterlab
jupyter lab Notebook_Klasifikacija_Radionica.ipynb
```

On Windows, activate the environment with `.venv\Scripts\activate`.
The requirements describe a supported runtime, not the original 2022 environment.

## Data source

The churn data comes from the
[Kaggle Customer Churn Prediction 2020 competition](https://www.kaggle.com/competitions/customer-churn-prediction-2020/data).
The target is `churn`, with values `yes` and `no`. The notebook uses numerical
features for an accessible first exercise and excludes categorical predictors.

Dataset and third party material rights remain with their respective owners.
