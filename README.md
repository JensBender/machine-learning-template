<!-- anchor tag for back-to-top links -->
<a name="readme-top"></a>

<!-- PROJECT LOGO -->
<div align="center">
  <a href="https://github.com/JensBender/rental-price-prediction">
    <img src="images/logo.jpg">
  </a>
  <p>
    <br />
    Developed a versatile ML template for streamlining data preprocessing, exploratory data analysis, and modeling for both regression and classification tasks. Integrated hyperparameter tuning, model evaluation, and selection, providing a flexible and efficient framework for ML workflows.
    <br />
  </p>
</div> 

---

<!-- TABLE OF CONTENTS -->
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


<!-- SUMMARY -->
## 🎯 Summary
This repository provides a comprehensive machine learning template designed to guide you through the key stages of the machine learning workflow, from data preprocessing to saving the final model. The template is organized into three key sections: **Data Preprocessing**, **Exploratory Data Analysis (EDA)**, and **Modeling**, with additional steps for **hyperparameter tuning**, **model evaluation** and **model selection**. It provides a flexible and robust foundation for any machine learning project and can be adapted to both regression and classification tasks. With this template, you can easily customize machine learning workflows to a variety of datasets and use cases, ensuring an efficient and reproducible approach to model development. 

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
- **Handle incorrect data types**: Convert string columns to numerical types (`pandas` `astype`) and datetime types (`pandas` `to_datetime`).
- **Extract features**:
    - Creat categorical features from string columns using custom functions with `pandas` `apply`.
    - Creat numerical features from string columns using custom functions with `pandas` `apply` and `re` for numeric pattern matching.
    - Creat boolean features from string columns using `lambda` functions with `pandas` `apply`.
- **Handle missing values**:
    - Delete rows with missing values using `pandas` `dropna`.
    - Impute missing values:
        - Numerical columns: Impute the median using `pandas` `fillna`.
        - Categorical columns: Impute the mode using `pandas` `fillna`.
- **Handle outliers**:
    - Remove univariate outliers using statistical methods (e.g., 3 standard deviations or 1.5 IQR) with a custom transformer class that inherits from `sklearn` `BaseEstimator` and `TransformerMixin`.
- **Save the preprocessed data**:
    - As a .csv file using `pandas` `to_csv`.
    - In a MySQL database table using `sqlalchemy`, `mysql-connector-python`, and `pandas` `to_sql`.
- **Split data** into training (e.g., 70%), validation (15%), and test (15%) sets using `sklearn` `train_test_split`.
- **Scale numerical features** using standard scaling with `sklearn` `StandardScaler` or min-max normalization with `MinMaxScaler`.
- **Encode categorical features** using one-hot encoding with `sklearn` `OneHotEncoder`.
- **Apply scaling and encoding together** using `sklearn` `ColumnTransformer`.

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## 🔍 Exploratory Data Analysis (EDA)
- **Univariate EDA**:
    - **Numerical columns**: Analyze descriptive statistics (e.g., mean, median, standard deviation) using `describe` from `pandas`. Visualize distributions with histograms using `histplot` from `seaborn` and `matplotlib`.
    - **Categorical columns**: Examine frequencies using `value_counts` from `pandas` and visualize them with bar plots or a bar plot matrix using `barplot` from `seaborn` and `subplot` from `matplotlib`. 
- **Bivariate EDA**:
    - **Two numerical columns**: Assess pairwise relationships with a correlation heatmap, scatterplots, or a scatterplot matrix. Use `corr` from `pandas`, `numpy`, `heatmap` and `scatterplot` from `seaborn`, and `subplot` from `matplotlib`.
    - **Numerical and categorical columns**: Explore relationships with group-wise statistics (e.g., mean or median by category) using `groupby` and `describe` from `pandas`. Visualize results with bar plots or a bar plot matrix using `barplot` from `seaborn` and `subplot` from `matplotlib`.

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## 🧠 Modeling
- **Train baseline models** to establish performance benchmarks:
    - **Regression task**: E.g., Linear Regression, Support Vector Regressor, Random Forest Regressor, Multi-Layer Perceptron Regressor, XGBoost Regressor (using `sklearn` and `xgboost`).
    - **Classification task**: E.g., Logistic Regression, Support Vector Classifier, Random Forest Classifier, Multi-Layer Perceptron Classifier, XGBoost Classifier (using `sklearn` and `xgboost`).
- **Perform hyperparameter tuning** (e.g., using grid search) with `GridSearchCV` from `sklearn`.
- **Select the final model** based on performance evaluation:
    - **Regression task**: E.g., using RMSE, MAPE, or R-squared (with `mean_squared_error`, `mean_absolute_percentage_error`, and `r2_score` from `sklearn`).
    - **Classification task**: E.g., using accuracy, precision, recall, or F1 score (with `classification_report`, `confusion_matrix`, and `ConfusionMatrixDisplay` from `sklearn`).
- **Save the final model** (e.g., as a .pkl file) using `pickle`.

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## 🚀 Getting Started
Follow these steps to set up the virtual environment, install the required packages, and, if needed, set up environment variables for the project.

### 📦 Set Up Virtual Environment
Follow the steps below to set up a Python virtual environment for this machine learning project and install the required dependencies.

- Ensure you have Python installed on your system.
- Create a virtual environment: 
  ```bash
  python -m venv machine-learning-venv
  ```
- Activate the virtual environment:
  - On Windows:
    ```bash
    machine-learning-venv\Scripts\activate
    ```
  - On macOS/Linux:
    ```bash
    source machine-learning-venv/bin/activate
    ```
- Ensure that `pip` is up to date:
  ```bash
  pip install --upgrade pip
  ```
- Install the required Python packages using the provided `requirements.txt` file:
  ```bash
  pip install -r requirements.txt
  ```
You're now ready to use the environment for your machine learning project! 

<p align="right">(<a href="#readme-top">back to top</a>)</p>


### 🗝️ Set Up Environment Variables
- If your project requires sensitive information, such as API keys or database credentials, it is good practice to store this information securely in a `.env` file. Example `.env` file content:
  ```
  # Your API key
  API_KEY="your_api_key_here"

  # Your SQL database credentials
  SQL_USERNAME="your_sql_username_here"
  SQL_PASSWORD="your_sql_password_here"
  ```
- Replace the placeholder values with your actual values.
- Add the `.env` file to your `.gitignore` to ensure it is not accidentally committed to version control.
- The environment variables stored in your `.env` file will be loaded into your environment using the `load_dotenv()` function from the `python-dotenv` library.

<p align="right">(<a href="#readme-top">back to top</a>)</p>


<!-- LICENSE -->
## ©️ License
This project is licensed under the [MIT License](LICENSE).

<p align="right">(<a href="#readme-top">back to top</a>)</p>


<!-- CREDITS -->
## 👏 Credits
This project was made possible with the help of the following resources:
- **Project Logo**: Created using the DALL·E image generator via [ChatGPT](https://chatgpt.com/) by OpenAI.

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
