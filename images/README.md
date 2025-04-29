# Images and Visualizations

This folder contains visualizations related to model performance, such as confusion matrices, absolute error maps, and summary charts.

## Running the Visualization Notebook

To generate the plots, run the `visualization_code.ipynb` notebook.  
The notebook expects the following eight CSV files to be available:

- **Confusion Matrices** (4 files)
  - `matrix_GaussianNB.csv`
  - `matrix_LogReg.csv`
  - `matrix_MLP.csv`
  - `matrix_MLPclassifier.csv`

- **Classification Reports** (4 files)
  - `classification_GaussianNB.csv`
  - `classification_LogReg.csv`
  - `classification_MLP.csv`
  - `classification_MLPclassifier.csv`

All required CSV files can be found in the [reports/](../reports) folder.

### Requirements
Make sure the following Python libraries are installed:
- pandas
- numpy
- seaborn
- matplotlib

### Steps to Run
1. Upload all eight required CSV files from the `reports/` folder into your environment (for example, into Google Colab via the "Files" panel).
2. Open and run each cell of `visualization_code.ipynb`.
