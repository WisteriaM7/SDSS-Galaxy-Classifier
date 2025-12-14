# 📄 SDSS Galaxy Classification

## 1. Introduction

### 1.1 Project Title
Sloan Digital Sky Survey (SDSS) Galaxy Classification using Machine Learning

### 1.2 Objective
The primary objective of this project is to develop and deploy a predictive model capable of classifying galaxies into one of two categories: **Starforming** or **Starbursting**, based on their observed photometric and spectroscopic properties derived from the SDSS dataset.

### 1.3 Scope
The scope covers data preprocessing (assumed to be done offline), model training (represented by `kmodel.pkl`), and the development of a basic web application using Flask for interactive classification and deployment.

## 2. System Architecture

### 2.1 Overview
The system employs a client-server architecture where a web frontend captures galaxy parameters and a Python Flask backend performs the machine learning prediction.



### 2.2 Technology Stack
* **Backend:** Python 3, Flask, NumPy, Pandas, Scikit-learn
* **Frontend:** HTML5, CSS3
* **Model Persistence:** Pickle
* **Deployment Environment:** Local server (`app.run`)

## 3. Machine Learning Model

### 3.1 Model Source
A pre-trained model file, `kmodel.pkl`, is loaded at application startup. (It is assumed this is a supervised classification model, such as K-Nearest Neighbors, SVM, or Random Forest).

### 3.2 Feature Engineering and Selection
The model relies on 10 specific photometric and spectroscopic features extracted from the SDSS data. These features were selected based on their discriminatory power between the two galaxy types.

| Feature Name | Description | Data Type |
| :--- | :--- | :--- |
| `i`, `z` | Instrumental magnitude in the i and z filters. | Float (Input) |
| `modelFlux_z` | Model-fit flux in the z filter. | Float (Input) |
| `petroRad_g`, `petroRad_r` | Petrosian radius in the g and r filters. | Float (Input) |
| `petroFlux_z` | Petrosian flux in the z filter. | Float (Input) |
| `petroR50_u`, `petroR50_g`, `petroR50_i`, `petroR50_r` | Petrosian radius containing 50% of the light in the specified filters. | Float (Input) |

### 3.3 Prediction Logic (`/predict` route)
1.  User inputs 10 values via the `/input` form.
2.  The Flask route `/predict` receives the data via `POST` request.
3.  Inputs are converted into a Pandas DataFrame, ensuring the column names and order match the training data.
4.  The model makes a prediction: `prediction = model.predict(input_df)[0]`.
5.  The numerical output is mapped to a human-readable result:
    * `0` $\rightarrow$ "starforming"
    * `1` $\rightarrow$ "starbursting"
6.  The result is rendered on `output.html`.

## 4. Web Application Design

The application utilizes a three-page structure:

| Template File | Flask Route | Purpose | Description |
| :--- | :--- | :--- | :--- |
| `home.html` | `/` | **Home Page** | Provides project introduction, objectives, and a link to start the prediction. |
| `input.html` | `/input` | **Input Form** | Presents a table-based form for users to enter the 10 required galaxy parameters. |
| `output.html` | `/predict` | **Result Page** | Displays the `{{ prediction }}` result (Starforming or Starbursting) and includes a button to return to the input form. |

### 4.1 Styling and User Experience (UX)
The application uses a consistent, space-themed color palette (`#301CA0`, `#7132CA`, `#F29AAE`) across all pages to provide a unified and visually appealing experience appropriate for an astronomy-related project.

## 5. Deployment and Execution

### 5.1 Required Files
The following files must be present in the project directory:
* `app.py`
* `RF.pkl`
* `templates/home.html`
* `templates/input.html`
* `templates/output.html`
* (Optional but Recommended) `requirements.txt`

### 5.2 Execution Steps
1.  Ensure Python and dependencies are installed.
2.  Open terminal in the project root directory.
3.  Execute the script: `python app.py`
4.  Navigate to `http://127.0.0.1:2222/` in a web browser.

## 6. Conclusion

This project successfully integrates a trained machine learning model with a web interface, demonstrating an effective method for applying data science to complex astronomical classification problems.
