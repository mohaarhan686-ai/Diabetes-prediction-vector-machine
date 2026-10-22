Diabetes Prediction Using Support Vector Machine (SVM)
A machine learning project that uses a Support Vector Machine (SVM) classifier to predict whether a person may have diabetes based on selected medical and demographic measurements. The project uses the Pima diabetes dataset and demonstrates data exploration, feature standardization, model training, evaluation, and prediction for a new input.
Important: This is an educational machine learning project, not a medical diagnostic tool. Predictions should not be used to diagnose or rule out diabetes. Consult a qualified healthcare professional for medical assessment.


Project Overview
Diabetes is a long-term health condition that affects how the body regulates blood glucose. This project explores how supervised machine learning can classify records into two outcome categories using available input features.

The model learns patterns from labeled examples and predicts an outcome for a new set of measurements.
Key Features
- Exploratory analysis of the dataset
- Separation of input features and target labels
- Feature standardization with StandardScaler
- Train-test split with stratification
- Linear Support Vector Machine classifier
- Model evaluation using accuracy score
- Example prediction for a single input record
Workflow
Pima Diabetes Dataset
        |
        v
Data Loading and Exploration
        |
        v
Feature / Target Separation
        |
        v
Feature Standardization
        |
        v
Train-Test Split (80% / 20%)
        |
        v
Train Linear SVM Classifier
        |
        v
Evaluate Model Accuracy
        |
        v
Predict Outcome for New Input
Dataset
The notebook uses the Pima diabetes dataset, loaded from a file named diabetes.csv.
- Records: 768
- Input features: 8
- Target column: Outcome
- Outcome 0: Non-diabetic class in the dataset
- Outcome 1: Diabetic class in the dataset
Input Features
Feature	Description
Pregnancies	Number of pregnancies
Glucose	Glucose measurement
BloodPressure	Blood pressure measurement
SkinThickness	Skin thickness measurement
Insulin	Insulin measurement
BMI	Body Mass Index
DiabetesPedigreeFunction	Dataset feature related to family history
Age	Age in years


The dataset's Outcome column is the target label used during supervised learning; it is not an input feature.
Technologies Used
- Python — programming language
- Pandas — dataset loading and analysis
- NumPy — numerical operations
- Scikit-learn — preprocessing, model training, and evaluation
- Google Colab / Jupyter Notebook — interactive development environment
Machine Learning Approach
1. Data Loading and Exploration
The CSV dataset is loaded with Pandas. The notebook examines sample rows, dataset dimensions, descriptive statistics, and the distribution of target labels.
2. Feature and Target Separation
The eight input columns are assigned to X, while the Outcome column is assigned to Y.
3. Feature Standardization
StandardScaler transforms the input features to a common scale. This is important for SVM models because feature magnitudes can influence model behavior.
4. Train-Test Split
The notebook uses an 80/20 train-test split with stratification and random_state=2. This creates training data for fitting the model and held-out data for evaluation.
5. Model Training
A linear SVM classifier is created using:
from sklearn import svm

classifier = svm.SVC(kernel="linear")
classifier.fit(X_train, Y_train)
6. Evaluation
The notebook calculates accuracy by comparing the model's predictions with the test labels.

Recorded test accuracy: 77.27% on the notebook's test split. This is the result recorded in the current notebook, not a guarantee of performance on other data. Accuracy alone does not show how well the model identifies each class; additional metrics such as precision, recall, F1-score, and a confusion matrix would provide a fuller evaluation.
Getting Started
Option 1: Run in Google Colab
1. Open the notebook using the Open in Google Colab badge above.
2. Upload diabetes.csv to the Colab session if it is not already available.
3. Run the notebook cells in order, starting with imports and dataset loading.
4. Review the evaluation output and sample prediction.
Option 2: Run Locally
Requirements
- Python 3.9 or later
- Jupyter Notebook or JupyterLab
- The diabetes.csv dataset file
Installation
Clone the repository:
git clone https://github.com/mohaarhan686-ai/Diabetes-prediction-vector-machine.git
cd Diabetes-prediction-vector-machine
Install the required libraries:
pip install pandas numpy scikit-learn jupyter
Place diabetes.csv in the project directory. If you use the notebook locally, update the dataset-loading path to match the file location. Then start Jupyter:
jupyter notebook
Open Diabetes_prediction_vector_machine.ipynb and run the cells in sequence.
Example Prediction
The notebook demonstrates prediction using one record with the following feature order:
input_data = (5, 166, 72, 19, 175, 25.8, 0.587, 51)
The input is converted to an array, standardized using the fitted scaler, and passed to the trained classifier. In the notebook's recorded example, the output is 1, which maps to the diabetic class in the dataset.

Note: This example illustrates model inference only. It is not a clinical conclusion about any person.
Project Structure
Diabetes-prediction-vector-machine/
├── Diabetes_prediction_vector_machine.ipynb
├── diabetes.csv
└── README.md
The CSV file must be added to the repository or supplied separately for the notebook to run. Adjust the structure above if your actual repository uses different filenames or folders.
Limitations and Future Improvements
Potential improvements include:
- Use a scikit-learn Pipeline to keep scaling and model training together and avoid data leakage.
- Fit the scaler on training data only, then transform both training and test data.
- Evaluate precision, recall, F1-score, and a confusion matrix.
- Use cross-validation and tune SVM hyperparameters.
- Investigate how missing or zero-valued measurements are handled.
- Test performance on appropriate independent data before making any real-world claims.
Disclaimer
This repository is intended for learning and experimentation with supervised machine learning. It has not been established as a clinically validated diagnostic system. Do not use its predictions to make healthcare decisions.
Author
Mohd Arhan

GitHub: @mohaarhan686-ai
If you find this project useful for learning, feel free to explore the notebook and build on it.
