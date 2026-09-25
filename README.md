# Used Car Price Analysis & Prediction

**Jonathan Zada · Solo academic project · Grade: 100/100**

An analysis of 10,000 used-car records combining exploratory statistics, bootstrap comparisons, price-bracket classification, and exact-price regression. Linear regression and KNN regression are compared with a mean-price baseline.

[Read the notebook](Data_Analysis_Project.ipynb)

## Analysis

- Explore vehicle attributes, price distributions, and associations using Pandas, Matplotlib, and Seaborn.
- Estimate bootstrap confidence intervals for mean-price differences across fuel and transmission categories.
- Encode categorical variables and select features using training-set correlations.
- Compare six-feature and four-feature KNN classifiers, selecting k from 1–50 using 10-fold cross-validation.
- Report accuracy, macro precision, macro recall, and confusion matrices.

## Recorded results in the updated notebook

| Model | Selected k | Mean CV accuracy | Test accuracy | Macro precision | Macro recall |
| --- | ---: | ---: | ---: | ---: | ---: |
| Six features | 38 | 76.65% | 77.35% | 78.03% | 77.25% |
| Four features | 29 | 74.325% | 74.9% | 74.94% | 74.70% |

### Exact-price regression

| Model | Test R² | Test RMSE (USD) | Test MAE (USD) |
| --- | ---: | ---: | ---: |
| Mean-price baseline | -0.001 | 2,821.766 | 2,265.524 |
| Linear regression | 0.877 | 989.819 | 790.652 |
| KNN regression (k = 19) | 0.858 | 1,063.078 | 847.932 |

Linear regression uses 19 encoded predictors. KNN regression uses six selected features and chooses k from 1–50 by 10-fold CV RMSE; the recorded best CV RMSE is $1,075.61. The notebook also includes predicted-versus-actual and residual plots.

The saved run uses 8,000 training and 2,000 test records. The six-feature model uses engine capacity, make year, owner count, fuel efficiency, and two fuel-type indicators. The smaller model omits fuel efficiency and the petrol indicator.

These are preserved notebook outputs, not newly reproduced results. The course grade is supplied by the author. Runtime was not measured. Results describe this dataset and do not establish causal relationships or real-market forecasting performance.

## Dataset

Source: [Rohith Anand — Used Car Price Prediction, Kaggle](https://www.kaggle.com/datasets/therohithanand/used-car-price-prediction/data).

Download `used_car_price_dataset_extended.csv` and place it beside the notebook. The author's supplied file contains 10,000 records and 12 columns, including the original `price_usd` target. `mileage_kmpl` is fuel efficiency, not odometer distance.

The CSV is not redistributed here; consult Kaggle for the dataset's current terms. Notebook previews retain the original small tabular samples and aggregate plots.

## Open locally

```sh
python -m venv .venv
# Activate .venv using the command appropriate for your operating system.
python -m pip install -r requirements.txt
jupyter lab Data_Analysis_Project.ipynb
```

Run cells from top to bottom with the CSV in the same directory. Dependencies are listed without pinned versions because the original environment was not recorded. The updated notebook sets SEED = 42, seeds NumPy, and supplies random_state for shuffling and splitting. Exact reproduction still depends on the data, environment, and execution order.

## Publication scope

This repository contains the author's updated notebook exactly as supplied, including its code, narrative, plots, and stored outputs. It adds regression, expands the neighbor search, recenters bootstrap distributions for the reported p-values, and corrects the transmission comparison order. The grade above refers to the coursework; it is not a separate assessment of this updated edition.

Results have not been independently rerun for this publication. The data may be synthetic, as discussed in the notebook, but its provenance is not established here. Associations and regression coefficients do not establish causal effects.

Further methodological review remains deferred: classification thresholds use the full dataset, scaling occurs before CV folds, and multiple model variants are compared on test data. No measured runtime result supports a speed claim. Earlier notebook versions remain available in Git history.
