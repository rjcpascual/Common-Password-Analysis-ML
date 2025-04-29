# Password Strength Classification

This repository contains a full workflow for classifying password strength using machine learning models. The project covers data preprocessing, model training, evaluation, and result analysis.

## Project Structure

- **data/**  
  Contains the original training and testing datasets:
  - `training-password-data.csv`
  - `testing-password-data.csv`
  - `full-password-dataset.csv`

- **images/**  
  Images related to the confusion matrices and model performance. Includes a Jupyter Notebook that contains code to create the visualizations.

- **models/**  
  Exported machine learning models as Jupyter Notebooks (.ipynb).

- **reports/**  
  Classification reports and confusion matrices for each model in CSV format.

- **PASSWORD-STRENGTH.knwf**  
  KNIME workflow used for initial data preprocessing and preparation.

- **RESULTS.md**  
  Summary of the overall model performance and findings.  
  [View RESULTS.md here](./RESULTS.md)

## Models Implemented

Four machine learning models were developed and evaluated:
- Gaussian Naive Bayes
- Logistic Regression
- Multi-Layer Perceptron (MLP)
- MLPClassifier (optimized variant)

Each model's classification report and confusion matrix are available under the `reports/` directory.

## Running the Models

Each model expects the following files available in the working environment:
- `training-password-data.csv`
- `testing-password-data.csv`

### Running in Google Colab
1. Upload `training-password-data.csv` and `testing-password-data.csv` manually through the "Files" panel in Colab.
2. Ensure the uploaded files are located in the current working directory (usually `/content/`).
3. Run the code
