# Forest Fire Weather Index (FWI) Prediction Web App

This is a Flask-based web application that predicts the Fire Weather Index (FWI) using a trained Ridge Regression model. The model uses weather and environmental parameters to make the prediction.

## 📁 Project Structure

├── application.py # Main Flask application
├── templates/
│ ├── home.html # Web form for input
│ └── index.html # Landing page (not included in current files)
├── models/
│ ├── ridge.pkl # Trained Ridge Regression model
│ └── scaler.pkl # StandardScaler fitted to training data
└── README.md # Project documentation

## ⚙️ Requirements

- Python 3.7+
- Flask
- scikit-learn
- pandas
- numpy

Install dependencies:

```bash
pip install flask scikit-learn pandas numpy
```
🚀 Running the App
1. Ensure the following files exist inside the models/ directory: ridge.pkl, scaler.pkl

2. Start the Flask application: ```python application.py```

3. Open a browser and go to: ```http://127.0.0.1:5000/predictdata```
    This will load the input form for prediction.

🧠 Model Inputs
The form accepts the following 11 numerical inputs:

Temperature

RH (Relative Humidity)

Ws (Wind Speed)

Rain

FFMC (Fine Fuel Moisture Code)

DMC (Duff Moisture Code)

DC (Drought Code)

ISI (Initial Spread Index)

BUI (Build Up Index)

Classes (Fire class encoding)

Region (Region code)

Make sure all fields are filled with valid numbers before submitting.

🔧 Error Handling
If any field is left blank or has non-numeric input, the application will return an error.

Server-side validation is included to help catch input issues.

💡 Notes
A GET request to /predictdata loads the input form (home.html).

A POST request processes the form data, makes the prediction, and returns the result in the same template.

index.html is referenced but not included — you can customize it as a landing page.
