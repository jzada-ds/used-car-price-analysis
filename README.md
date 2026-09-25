# Used Car Price Analysis & Classification

**Jonathan Zada · Solo academic project · Grade: 100/100**

An exploratory analysis of 10,000 used-car records followed by K-nearest-neighbor classification into three price brackets. The model classifies budget, mid-range, and high-price groups; it does not estimate an exact dollar price.

[Read the notebook](Data_Analysis_Project.ipynb)

## Analysis

- Explore vehicle attributes, price distributions, and associations using Pandas, Matplotlib, and Seaborn.
- Estimate bootstrap confidence intervals for mean-price differences across fuel and transmission categories.
- Encode categorical variables and select features using training-set correlations.
- Compare six-feature and four-feature KNN classifiers, selecting k from 1–24 using 10-fold cross-validation.
- Report accuracy, macro precision, macro recall, and confusion matrices.

## Recorded coursework results

| Model | Selected k | Mean CV accuracy | Test accuracy | Macro precision | Macro recall |
| --- | ---: | ---: | ---: | ---: | ---: |
| Six features | 24 | 76.51% | 76.4% | 77.64% | 76.41% |
| Four features | 20 | 74.04% | 73.8% | 74.20% | 73.78% |

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

Run cells from top to bottom with the CSV in the same directory. Dependencies are listed without pinned versions because the original environment was not recorded. Randomized splits and bootstraps are unseeded, so reruns can differ from saved outputs.

## Publication scope

This edition updates presentation, dataset attribution, and interpretation only. Analysis code and saved outputs are unchanged from the supplied coursework notebook. Methodological revisions are deferred; the original p-value calculations and evaluation procedure should not be treated as a corrected benchmark. Some code was adapted from course lectures, as attributed within the notebook.
