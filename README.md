# 🌌 SDSS Galaxy Classification using Machine Learning

## Project Overview

This project implements a machine learning model to classify galaxies from the **Sloan Digital Sky Survey (SDSS)** astronomical data. The primary goal is to predict whether a given galaxy is **Starforming** or **Starbursting** based on its photometric properties and redshift.

The application provides a user-friendly web interface (built with **Flask**) where users can input key observational parameters of a galaxy and receive an instant prediction of its classification.

## ✨ Features

* **Interactive Web Interface:** User input form for entering galaxy features.
* **Backend Prediction:** Uses a pre-trained machine learning model (`kmodel.pkl`) to classify the galaxy.
* **Data Driven:** Classification is based on real SDSS photometric and spectroscopic parameters.

## 💻 Tech Stack

| Component | Technology | Role |
| :--- | :--- | :--- |
| **Backend Framework** | Flask (Python) | Routing, handling form submission, and serving predictions. |
| **Machine Learning** | Scikit-learn, Pandas | Model training (assumed to be K-Nearest Neighbors based on filename `kmodel.pkl`) and data manipulation. |
| **Model Persistence** | Pickle | Serialization and loading of the pre-trained model. |
| **Frontend** | HTML, CSS | Structure and styling of the web interface (Home, Input, Result pages). |

## 🚀 Getting Started

These instructions will get a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

You need to have Python and a package manager (pip) installed.

```bash
# Check your Python version
python --version
