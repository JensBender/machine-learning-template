<!-- anchor tag for back-to-top links -->
<a name="readme-top"></a>

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
    <a href="#-getting-started">Getting Started</a>  
    <ul>
        <li><a href="#-set-up-virtual-environment">Set Up Virtual Environment</a></li>
        <li><a href="#️-set-up-environment-variables">Set Up Environment Variables</a></li>
    </ul>
  </li>
  <li>
    <a href="#️-license">License</a>
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


## Data Preprocessing

The preprocessing section includes essential data cleaning and transformation steps:

- **Load data** from a .csv file using `read_csv` from `pandas` or from a MySQL database table using `sqlalchemy`, `mysql-connector-python`, and `read_sql` from `pandas`.
- **Remove duplicates** (e.g., based on the ID column) using `drop_duplicates` from `pandas`.
- **Handle incorrect data types** (e.g., convert string columns to numerical or datetime columns) using `astype` or `to_datetime` from `pandas`.
- **Extract features** (e.g., create categorical, numerical, or boolean features from string columns) using custom functions with `apply` from `pandas`, `lambda` functions, and `re` for pattern matching.
- **Handle missing values** (e.g., through deletion, median imputation for numerical columns, or mode imputation for categorical columns) using `dropna` or `fillna` from `pandas`.
- **Handle outliers** (e.g., remove them using the 3SD method or 1.5 IQR method) with a custom transformer class utilizing `BaseEstimator` and `TransformerMixin` from `sklearn`.
- **Save the preprocessed data** as a .csv file using `to_csv` from `pandas` or in a MySQL database table using `sqlalchemy`, `mysql-connector-python`, and `to_sql` from `pandas`.
- **Split data** into training (e.g., 70%), validation (15%), and test (15%) sets using `train_test_split` from `sklearn`.
- **Scale numerical features** (e.g., using standard scaling or min-max normalization) with `StandardScaler` or `MinMaxScaler` from `sklearn`.
- **Encode categorical features** (e.g., using one-hot encoding) with `OneHotEncoder` from `sklearn`.

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Exploratory Data Analysis (EDA)
- Analyze descriptive statistics (e.g., `mean`, `median`, `standard deviation`) of numerical columns and visualize distributions (e.g., using `histograms`).
- Examine frequencies of categorical columns and visualize them (e.g., using `bar plots` or a `bar plot matrix`).
- Assess bivariate relationships between numerical columns (e.g., using a `correlation heatmap`, `scatterplots`, or a `scatterplot matrix`).
- Explore relationships between numerical and categorical columns with group-wise statistics (e.g., `mean` or `median` by category) and visualize them (e.g., through `bar plots` or a `bar plot matrix`).

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
