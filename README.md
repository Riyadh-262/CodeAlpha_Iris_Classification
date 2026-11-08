Iris Flower Classification
Internship Project --- CodeAlpha | Task 1

A supervised machine-learning project that predicts the species of an
Iris flower from four measurements: sepal length, sepal width, petal
length, and petal width. The project uses a Support Vector Machine (SVM)
classifier with an RBF kernel and feature standardization.
Project Overview
The objective is to build and evaluate a classification model that can
distinguish among three Iris species:
- Setosa
- Versicolor
- Virginica
The workflow is implemented in the Jupyter Notebook
iris-flower-classification.ipynb.
Dataset
The project uses Iris.csv, containing 150 records and 6
columns:

  Column            Description
  Id              Record identifier; excluded from model training
SepalLengthCm   Sepal length in centimetres
SepalWidthCm    Sepal width in centimetres
PetalLengthCm   Petal length in centimetres
PetalWidthCm    Petal width in centimetres
Species         Target class

Each species has 50 records. The inspected dataset contains no missing
values in these columns.
Methodology
1. Load the data: Read Iris.csv into a pandas DataFrame.
2. Prepare features and target: Remove Id because it is an
   identifier, not a flower measurement. Use the four measurement
   columns as features (X) and Species as the target (y). Remove
   the Iris- prefix from target labels.
3. Split the data: Use an 80:20 train-test split with
   random_state=42 and stratify=y. This creates 120 training
   records and 30 testing records while preserving class proportions.
4. Build the model: Create a scikit-learn pipeline containing:
   - StandardScaler to standardize feature values.
   - SVC(kernel="rbf") to classify samples using a Support Vector
     Machine with a radial basis function kernel.
5. Train and predict: Fit the pipeline on the training set and
   predict the species of the test set.
6. Evaluate: Calculate accuracy, precision, recall, F1-score, and a
   confusion matrix.
7. Try a new sample: Predict the species for a sample with
   measurements [5.1, 3.5, 1.4, 0.2].
Results
The saved notebook reports:
- Test accuracy: 96.67%
- Test samples: 30
- Correct predictions: 29 out of 30
Classification report:

  Species        Precision   Recall   F1-score   Support
  Setosa              1.00     1.00       1.00        10
Versicolor          1.00     0.90       0.95        10
Virginica           0.91     1.00       0.95        10

The notebook also generates and saves a confusion-matrix visualization
as confusion_matrix.png. The sample flower is predicted as Setosa.

Note: These are the results recorded in the supplied notebook.
Re-running the notebook may reproduce them when the same dataset,
library behavior, and split settings are used.
Technologies and Libraries
- Python
- pandas
- NumPy
- Matplotlib
- Seaborn
- scikit-learn
- Jupyter Notebook / Kaggle Notebooks
How to Run
Option A: Kaggle Notebooks
1. Upload or add the Iris dataset to a Kaggle Notebook.
2. Open iris-flower-classification.ipynb.
3. Confirm the dataset path in the CSV-loading cell. The supplied
   notebook currently uses:
   df = pd.read_csv("/kaggle/input/datasets/riyadhdata262/iris-dataset/Iris.csv")
4. If your Kaggle dataset has a different path, replace it with the
   path shown in the notebook's /kaggle/input directory.
5. Run all cells from top to bottom.
Option B: Run Locally
1. Download or clone this project and keep Iris.csv and the notebook
   in the same folder.
2. Install the required packages:
   pip install numpy pandas matplotlib seaborn scikit-learn jupyter
3. In the notebook, change the data-loading line to:
   df = pd.read_csv("Iris.csv")
4. Start Jupyter:
   jupyter notebook
5. Open iris-flower-classification.ipynb and run all cells.
Repository Structure
iris-flower-classification/
├── Iris.csv
├── iris-flower-classification.ipynb
├── README.md
├── PROJECT_DESCRIPTION.md
└── confusion_matrix.png   # generated when the notebook is run
Learning Outcomes
- Understanding a supervised multi-class classification problem.
- Separating input features from a target variable.
- Performing a stratified train-test split.
- Understanding why feature scaling is useful for SVM.
- Building a reusable preprocessing-and-model pipeline.
- Evaluating classification performance with multiple metrics.
- Interpreting a confusion matrix and making predictions for a new
  sample.
Limitations and Future Improvements
- The dataset is small and clean; performance on real-world flower
  images or measurements may differ.
- The notebook uses the default SVC settings apart from the RBF
  kernel. Hyperparameter tuning has not been documented as part of
  this implementation.
- Future work could compare SVM with Logistic Regression, K-Nearest
  Neighbors, Decision Tree, and Random Forest; use cross-validation
  and hyperparameter search; and add a more detailed exploratory data
  analysis.
Author
Riyadh Hossain

Prepared as an internship task submission for CodeAlpha --- Iris
Flower Classification.
