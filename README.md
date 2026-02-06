<!-- anchor tag for back-to-top links -->
<a name="readme-top"></a>

<!-- HEADER IMAGE  -->
<img src="images/header-image.webp">

<!-- SHORT SUMMARY  -->
Designed a versatile machine learning template for streamlining data preprocessing, exploratory data analysis, and modeling for both regression and classification tasks on structured tabular data. Integrated hyperparameter tuning and model evaluation, providing a flexible and efficient framework for ML workflows.


## 📋 Table of Contents
<ol>
  <li>
    <a href="#-summary">Summary</a>
    <ul>
      <li><a href="#️-built-with">Built With</a></li>
    </ul>
  </li>
  <li>
    <a href="#-data-preprocessing">Data Preprocessing</a>
  </li>
  <li>
    <a href="#-exploratory-data-analysis-eda">Exploratory Data Analysis (EDA)</a>
  </li>
  <li>
    <a href="#-modeling">Modeling</a>
  </li>
  <li>
    <a href="#-getting-started">Getting Started</a>  
    <ul>
        <li><a href="#-set-up-virtual-environment">Set Up Virtual Environment</a></li>
        <li><a href="#️-set-up-environment-variables">Set Up Environment Variables</a></li>
    </ul>
  </li>
  <li>
    <a href="#️-license">License</a>
  </li>
  <li>
    <a href="#-credits">Credits</a>
  </li>
</ol>


## 🎯 Summary
This repository provides a comprehensive **machine learning template** in a Jupyter Notebook file to streamline the key stages of the machine learning workflow for tabular data:

- **Data Preprocessing**:
  - Load, clean, transform, and save data using `pandas` and `sklearn`.
  - Handle duplicates, incorrect data types, missing values, and outliers.
  - Extract features, scale numerical features, and encode categorical features.
  - Split data into training, validation, and test sets.
- **Exploratory Data Analysis (EDA)**:
  - Analyze descriptive statistics using `pandas` and `numpy`.
  - Visualize distributions, correlations, and relationships using `seaborn` and `matplotlib`.
- **Modeling**:
  - Train baseline models and perform hyperparameter tuning for regression and classification tasks with `sklearn` and `xgboost`.
  - Evaluate regression (RMSE, MAPE, R-squared) and classification models (accuracy, precision, recall, F1-score).
  - Visualize feature importance, show model prediction examples, and save the final model with `pickle`.

This template provides a flexible, customizable foundation for various datasets and use cases, making it an ideal starting point for efficient and reproducible machine learning projects. It is specifically tailored to structured tabular data (e.g., .csv, .xls, or SQL tables) using Pandas and Scikit-learn. It is not optimized for text, image, or time series data, which require specialized preprocessing, models, and tools (e.g., TensorFlow, PyTorch).

### 🛠️ Built With
- [![Python][Python-badge]][Python-url]
- [![Pandas][Pandas-badge]][Pandas-url]
- [![Matplotlib][Matplotlib-badge]][Matplotlib-url] 
- [![Seaborn][Seaborn-badge]][Seaborn-url]
- [![scikit-learn][scikit-learn-badge]][scikit-learn-url]
- [![Jupyter Notebook][JupyterNotebook-badge]][JupyterNotebook-url]

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## 🧹 Data Preprocessing
Use `pandas`, `sklearn`, `sqlalchemy`, and `mysql-connector-python` for data loading, cleaning, transformation, and saving.
- **Load data**:
    - From a .csv file using `pandas` `read_csv`.
    - From a MySQL database table using `sqlalchemy`, `mysql-connector-python`, and `pandas` `read_sql`.
- **Remove duplicates**:
    - Drop duplicate rows (e.g., based on the ID column) using `pandas` `drop_duplicates`.
- **Handle incorrect data types**:
    - Convert string columns to numerical types (`pandas` `astype`) and datetime types (`pandas` `to_datetime`).
- **Extract features**:
    - Create categorical features from string columns using custom functions with `pandas` `apply`.
    - Create numerical features from string columns using custom functions with `pandas` `apply`, and `re` for numeric pattern matching.
    - Create boolean features from string columns using `lambda` functions with `pandas` `apply`.
- **Handle missing values**:
    - Delete rows with missing values using `pandas` `dropna`.
    - Impute missing values: Fill in the median for numerical columns or the mode for categorical columns using `pandas` `fillna`.
- **Handle outliers**:
    - Remove univariate outliers using statistical methods (e.g., 3 standard deviations or 1.5 IQR) with a custom transformer class that inherits from `sklearn` `BaseEstimator` and `TransformerMixin`.
- **Save the preprocessed data**:
    - As a .csv file using `pandas` `to_csv`.
    - In a MySQL database table using `sqlalchemy`, `mysql-connector-python`, and `pandas` `to_sql`.
- **Train-validation-test split**:
    - Split data into training (e.g., 70%), validation (15%), and test (15%) sets using `sklearn` `train_test_split`.
- **Polynomial features**:
    - Create polynomial features using `sklearn` `PolynomialFeatures`.
- **Feature scaling and encoding**:
    - Scale numerical features using standard scaling with `sklearn` `StandardScaler` or min-max normalization with `MinMaxScaler`.
    - Encode categorical features:
        - Nominal features: Use one-hot encoding with `sklearn` `OneHotEncoder`.
        - Ordinal features: Use ordinal encoding with `sklearn` `OrdinalEncoder`.
    - Apply scaling and encoding together using `sklearn` `ColumnTransformer`.

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## 🔍 Exploratory Data Analysis (EDA)
Use `pandas`, `numpy`, `seaborn`, and `matplotlib` for statistical analysis and visualizations.
- **Univariate EDA**:
    - **Numerical columns**:
        - Analyze descriptive statistics (e.g., mean, median, standard deviation) using `pandas` `describe`.
        - Visualize distributions with histograms using `seaborn` `histplot` and `matplotlib`.
    - **Categorical columns**:
        - Examine frequencies using `pandas` `value_counts`.
        - Visualize frequencies with bar plots (`seaborn` `barplot`) or a bar plot matrix (`matplotlib` `subplot`). 
- **Bivariate EDA**:
    - **Two numerical columns**:
        - Analyze pairwise relationships with a correlation matrix (`pandas` `corr` and `numpy`) and visualize them with a heatmap (`seaborn` `heatmap`).
        - Visualize relationships with scatterplots (`seaborn` `scatterplot`) or a scatterplot matrix (`matplotlib` `subplot`).
    - **Numerical and categorical columns**:
        - Explore relationships with group-wise statistics (e.g., mean or median by category) using `pandas` `groupby` and `describe`.
        - Visualize results with bar plots (`seaborn` `barplot`) or a bar plot matrix (`matplotlib` `subplot`).

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## 🧠 Modeling
Use `sklearn`, `xgboost`, and `pickle` for model training, evaluation, and saving.
- **Train baseline models**:
    - Establish performance benchmarks with the following models using `sklearn` and `xgboost`: Linear Regression, Logistic Regression, Elastic Net Regression, K-Nearest Neighbors, Support Vector Machine, Decision Tree, Random Forest, Multi-Layer Perceptron, and XGBoost.
- **Hyperparameter tuning**:
    - Perform hyperparameter tuning using grid search with `sklearn` `GridSearchCV` or random search with `RandomizedSearchCV`.
- **Model evaluation**:
    - Regression task:
        - Calculate metrics such as RMSE, MAPE, and R-squared with `sklearn` `mean_squared_error`, `mean_absolute_percentage_error`, and `r2_score`.
        - Analyze errors with residual plots, error distributions, and feature-error relationships using `pandas`, `seaborn`, and `matplotlib`.
    - Classification task:
        - Create classification report with metrics like accuracy, precision, recall, and F1-score using `sklearn` `classification_report`.
        - Analyze misclassifications using a confusion matrix with `sklearn` `confusion_matrix` and `ConfusionMatrixDisplay`.
        - Explore feature-misclassification relationships using `pandas`, `seaborn`, and `matplotlib`.
- **Feature importance**:
    - Visualize feature importances using `seaborn` and `matplotlib` or `xgboost` `plot_importance`.
- **Model prediction examples**:
    - Show illustrative examples of model predictions with best, worst, and typical cases using `pandas`.
- **Save the final model**:
    - Save the best-performing model as a .pkl file using `pickle`.

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## 🚀 Getting Started
Follow these steps to set up the virtual environment, install the required packages, and, if needed, set up environment variables for the project.

### 📦 Set Up Virtual Environment
Follow the steps below to set up a Python virtual environment for this machine learning project and install the required dependencies.

- Ensure you have Python installed on your system.
- Create a virtual environment: 
  ```bash
  python -m venv .venv
  ```
- Activate the virtual environment:
  - On Windows:
    ```bash
    .venv\Scripts\activate
    ```
  - On macOS/Linux:
    ```bash
    source .venv/bin/activate
    ```
- Ensure that `pip` is up to date:
  ```bash
  pip install --upgrade pip
  ```
- Install the required Python packages using the provided `requirements.txt` file:
  ```bash
  pip install -r requirements.txt
  ```
- Optionally, you can register the environment in Jupyter Notebook with a clear name like "Machine Learning Template" for Jupyter's kernel dropdown:
  ```bash
  pip install ipykernel
  python -m ipykernel install --user --name=machine-learning-template --display-name "Machine Learning Template"
  ```
You're now ready to use the environment for your machine learning project! 

<p align="right">(<a href="#readme-top">back to top</a>)</p>


### 🗝️ Set Up Environment Variables
- If your project requires sensitive information, such as API keys or database credentials, it is good practice to store this information securely in a `.env` file. Example `.env` file content:
  ```
  # Your API key
  API_KEY=your_api_key_here

  # Your SQL database credentials
  SQL_USERNAME=your_sql_username_here
  SQL_PASSWORD=your_sql_password_here
  ```
- Replace the placeholder values with your actual values.
- Add the `.env` file to your `.gitignore` to ensure it is not accidentally committed to version control.
- The environment variables stored in your `.env` file will be loaded into your environment using the `load_dotenv()` function from the `python-dotenv` library.

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## ©️ License
This project is licensed under the [MIT License](LICENSE).

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## 👏 Credits
This project was made possible with the help of the following resources:
- **Header and footer images**: Generated using the FLUX.1 [dev] image generator via [Hugging Face](https://huggingface.co/spaces/black-forest-labs/FLUX.1-dev) by [Black Forest Labs](https://blackforestlabs.ai/).

<p align="right">(<a href="#readme-top">back to top</a>)</p>


<!-- MARKDOWN LINKS -->
[Python-badge]: https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54
[Python-url]: https://www.python.org/
[Pandas-badge]: https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white
[Pandas-url]: https://pandas.pydata.org/
[Matplotlib-badge]: https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black
[Matplotlib-url]: https://matplotlib.org/
[Seaborn-badge]: https://img.shields.io/badge/seaborn-%230C4A89.svg?style=for-the-badge&logo=seaborn&logoColor=white
[Seaborn-url]: https://seaborn.pydata.org/
[scikit-learn-badge]: https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white
[scikit-learn-url]: https://scikit-learn.org/stable/
[JupyterNotebook-badge]: https://img.shields.io/badge/Jupyter-F37626.svg?style=for-the-badge&logo=Jupyter&logoColor=white
[JupyterNotebook-url]: https://jupyter.org/


<!-- FOOTER IMAGE  -->
<img src="images/footer-image.webp">
