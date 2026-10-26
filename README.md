# Diabetes Disease Progression Prediction Using ANN

## 📌 Project Overview

This project uses an Artificial Neural Network (ANN) to predict diabetes disease progression based on independent variables from the Diabetes dataset available in Scikit-learn.

The objective is to explore the dataset, preprocess the features, build and train neural network models, evaluate their performance, and experiment with different architectures to identify the most suitable model.

**Note:** This project predicts a continuous disease progression measure. It is a regression task, not a diabetes diagnosis or classification system.

## 🎯 Objectives

- Load and preprocess the Scikit-learn Diabetes dataset.
- Check for missing values and normalize input features.
- Perform Exploratory Data Analysis (EDA).
- Build and train ANN regression models.
- Evaluate models using MSE, RMSE, MAE, and R² score.
- Experiment with different network architectures and hyperparameters.
- Compare model performance and identify the best-performing configuration.

## 📊 Dataset

- **Source:** Scikit-learn built-in Diabetes dataset
- **Number of samples:** 442
- **Number of input features:** 10
- **Target variable:** Quantitative diabetes disease progression measure
- **Problem type:** Supervised regression

### Features

The dataset includes:

- Age
- Sex
- Body Mass Index (BMI)
- Average Blood Pressure
- Six blood serum measurements (`s1` to `s6`)

## 🛠️ Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- TensorFlow / Keras
- Jupyter Notebook

## ⚙️ Project Workflow

### 1. Data Loading and Preprocessing

- Loaded the Diabetes dataset using `sklearn.datasets.load_diabetes()`.
- Examined the dataset dimensions, data types, and statistical summary.
- Checked for missing values.
- Split the data into training and testing sets.
- Applied `StandardScaler` to normalize the input features.

### 2. Exploratory Data Analysis (EDA)

Performed visual analysis using:

- Feature distribution histograms
- Target variable distribution
- Correlation heatmap
- Scatter plots showing relationships between individual features and the target

### 3. ANN Model Development

Developed regression models using TensorFlow/Keras.

**Original ANN architecture:**
- Input layer: 10 features
- Hidden layer 1: 32 neurons, ReLU activation
- Hidden layer 2: 16 neurons, ReLU activation
- Output layer: 1 neuron, linear activation

**Improved ANN architecture:**
- Hidden layers with 64, 32, and 16 neurons
- ReLU activation
- Dropout regularization
- Target standardization
- Lower learning rate and early stopping

**Single-hidden-layer experiment:**

Also experimented with a simpler architecture containing one hidden layer to investigate whether reducing network complexity improves generalization.

### 4. Model Training

- Optimizer: Adam
- Loss function: Mean Squared Error (MSE)
- Additional metric: Mean Absolute Error (MAE)
- Training techniques: Validation split and early stopping in selected experiments

### 5. Model Evaluation

The models were evaluated on the held-out test set using:

- **MSE:** Mean Squared Error
- **RMSE:** Root Mean Squared Error
- **MAE:** Mean Absolute Error
- **R² Score:** Coefficient of determination

## 📈 Results

### Original ANN

| Metric | Result |
|---|---:|
| MSE | 2960.86 |
| RMSE | 54.41 |
| MAE | 43.47 |
| R² Score | 0.4412 |

### Model Comparison

| Model | MSE | MAE | R² Score |
|---|---:|---:|---:|
| Original ANN | 2960.86 | 43.47 | 0.4412 |
| Improved ANN | 3159.45 | 44.59 | 0.4037 |
| Single hidden layer (16 neurons) | 4864.87 | 53.85 | 0.0818 |

The single-hidden-layer result above corresponds to the 16-neuron Model V3 experiment. Results for the separate 32-neuron single-hidden-layer experiment should be added after evaluation.

### Best Model

The original ANN achieved the best performance among the three evaluated configurations, with an R² score of **0.4412** and an MSE of **2960.86**.

The experiments demonstrate that increasing model complexity or applying regularization does not necessarily improve predictive performance on a relatively small dataset.

## 💡 Key Learnings

- Feature scaling is important for ANN training.
- EDA helps understand feature distributions and relationships.
- ANN regression requires an appropriate output activation and loss function.
- Model performance should be evaluated using multiple regression metrics.
- A more complex neural network does not always perform better.
- Hyperparameter experiments should be compared using consistent test data.

## 🚀 How to Run the Project

1. Clone this repository:

   ```bash
   git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
   ```

2. Navigate to the project folder:

   ```bash
   cd YOUR_REPOSITORY
   ```

3. Install the required libraries:

   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn tensorflow jupyter
   ```

4. Start Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

5. Open the project notebook and run the cells in order.

## 📁 Project Structure

```text
diabetes-progression-ann/
│
├── diabetes_progression_ann.ipynb
├── README.md
└── requirements.txt
```

## ⚠️ Limitations

- The dataset contains only 442 samples.
- Performance may vary depending on the train/test split and model initialization.
- The reported results are experimental and are not evidence of clinical usefulness.
- The model is intended for educational purposes and should not be used for medical diagnosis or treatment decisions.

## 🔮 Future Improvements

- Tune the number of neurons and learning rate.
- Experiment with different activation functions.
- Apply cross-validation to assess performance stability.
- Compare the ANN against regression models such as Linear Regression, Ridge Regression, and Random Forest Regressor.
- Evaluate model performance across multiple random seeds.

## 👩‍💻 Author

**Aswathi MV**

- GitHub: https://github.com/aswathimv
- LinkedIn: https://www.linkedin.com/in/aswathi-mv1

## 📄 License

This project was developed for educational and academic purposes.
