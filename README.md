# Medication Classifier

Medication Classifier is a project that analyzes and predicts various aspects of pharmacy claims data, focusing on prior authorizations and medication refills. The project uses machine learning models and time series analysis to provide insights into approval probabilities, claim volumes, formulary details, and medication refill limitations.

## Table of Contents
- [Objective Overview](#objective-overview)
- [Key Insights](#key-insights)
- [Dataset](#dataset)
- [Anticipating PA Approval](#anticipating-pa-approval)
- [Predicting PA and Claim Volume](#predicting-pa-and-claim-volume)
- [Determining Formulary for Each Payer](#determining-formulary-for-each-payer)
- [Predicting Limits on Medication Refills](#predicting-limits-on-medication-refills)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Objective Overview

In the process of obtaining prescription medications, pharmacy claims against patients' insurance (payers) are generated. This project explores various classifiers to predict the likelihood of PA approval, forecasts future PA volumes using time series analysis, identifies the formulary for each payer, and predicts the limitations on medication refills.

### Key Insights
- A random forest model, identified through feature importance and ROC AUC score, proves effective in predicting prior authorization approval.
- Additive exponential smoothing offers an accurate forecast for monthly PA volume.
- Both Random Forest and LSTM models provide accurate daily PA volume forecasts.
- The formulary for each payer is successfully determined.
- Prediction of medication refill limitations is achieved.

## Dataset

The dataset used in this project is a simulated pharmacy claims dataset provided by [CoverMyMeds](https://covermymeds.com/). It contains over one million generated entries of simulated pharmacy claims data spanning the years 2016, 2017, and 2018.

## Anticipating PA Approval 

Not all prior authorizations (PA) get approved. Accurately predicting approval is essential to save time for doctors and ensure timely treatment for patients. A variety of models were evaluated on different feature subsets.

### Usage
- [pa_classifier.ipynb](pa_classifier.ipynb): Evaluates different models on various feature subsets for predicting PA approval.
- [pa_classifier_feature_importances.ipynb](pa_classifier_feature_importances.ipynb): Determines feature importance using drop-feature importances.
- [CMM_model_assessment.ipynb](CMM_model_assessment.ipynb): Examines the statistical significance of model results.

## Predicting PA and Claim Volume 

For healthcare technology companies, forecasting prior authorization volume is crucial for revenue prediction. Time series analysis, including exponential smoothing and ARIMA, was employed to predict monthly PA volume.

### Usage
- [volumeCI.ipynb](volumeCI.ipynb): Explores different time series analysis approaches for predicting monthly PA volume.
- [volume_rf.ipynb](volume_rf.ipynb): Uses random forest regression for daily volume forecasting.
- [volume_rnn.ipynb](volume_rnn.ipynb): Implements LSTM for daily volume prediction.

## Determining Formulary for Each Payer 

Understanding the formulary of each payer, indicating preferred drugs, is vital. This information aids in comprehending tiered costs and PA requirements. By analyzing reject codes, the formulary for each payer was identified.

### Usage
- [exploration.ipynb](exploration.ipynb): Provides details on payer-specific formulary outcomes.

## Predicting Limits on Medication Refills

A reject code 76 signifies a patient exceeding allowed medication refills. Assuming a Poisson distribution for the number of fills, a relation between average fills and limitations was inferred.

### Usage
- [number_of_fills.ipynb](number_of_fills.ipynb): Explores the relation between average fills and refill limitations.

## Getting Started

To get started with this project, follow these steps:

1. Clone the repository.
2. Install the required dependencies using `pip install -r requirements.txt`.
3. Open and run the Jupyter notebooks in the designated order.

## Contributing

Contributions are welcome! Feel free to open issues or submit pull requests.

## License

This project is licensed under the [MIT License](LICENSE).
