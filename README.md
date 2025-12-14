# SDSS-Galaxy-Classifier
##🌌 SDSS Galaxy Classification: Quick Read
###Project Goal
Classify galaxies from the Sloan Digital Sky Survey (SDSS) as either Starforming or Starbursting using a pre-trained machine learning model.

🛠️ Tech Stack
Backend: Flask (Python)

ML Model: Loaded via pickle (kmodel.pkl)

Frontend: HTML/CSS templates (home.html, input.html, output.html)

🚀 Setup & Run
Install dependencies: pip install flask pandas numpy scikit-learn

Run the application: python app.py

Access the app at: http://127.0.0.1:2222/

📊 Input Data
The model requires 10 SDSS photometric features (e.g., i, z magnitudes, petroRad, petroFlux) submitted via the web form.

🎯 Classification Output
The model predicts one of two classes:

Starforming (Class 0)

Starbursting (Class 1)
