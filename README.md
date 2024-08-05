# HLM-Stability-Prediction-Model
Machine learning-based prediction model for Human Liver Microsomal (HLM) stability prediction

## Introduction ## 

Welcome to our repository, here we provide machine learning model to efficiently predict the Human Liver Microsomal (HLM) stability of target drug compounds in early stage of drug discovery process. Liver microsomes are widely used in drug metabolism studies to predict the in vivo stability of compounds. Human liver microsomal stability testing is crucial for understanding how long a drug compound remains stable in the human liver before being metabolized.

## Classification criteria ##
**The model uses a half-life (t<sub>1/2</sub>) threshold:**

The model classifies a compound based on its predicted half-life value. If the half-life is greater than 30 minutes, the compound is classified as class 1; otherwise, it is classified as class 0. 

Additionally, the model provides the probability that each compound belongs to its respective class. If classified as class 1, the compound is considered stable, with the indicated probability.

## Dependencies ##

- Python ≥ 3.9
- scikit-learn ≥ 1.26.4
- numpy == 11.5.0
- hpsklearn == 1.0.3
- hyperopt == 0.2.7
- xgboost == 2.0.3
- rdkit
- pandas

## Execution ##
**To run the prediction:**

```
$ python model.py --prediction --file_name [filename]
```
<strong>Note:</strong> For the prediction step, prepare a .csv file containing SMILES without bioclass (e.g., test_set.csv)

**To run the validation:**

```
$ python model.py --validation --file_name [filename]
```
<strong>Note:</strong> For the validation step, prepare a .csv file containing SMILES with bioclass (0 or 1) (e.g., valid_set.csv)

**Output:**

Our model generates output in binary value (1 or 0), where 1 indicates compound to be stable, while 0 indicates unstable.

Additionally, the model provides the probability that each compound belongs to its respective class. If classified as class 1, the compound is considered stable, with the indicated probability.
 
**Please ensure that all the necessary files (HCLint.pkl, data_preprocessing.py, scaler, features.txt, input_file.csv, model.py) are kept in the working directory**
