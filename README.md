Housing Price Prediction
This project aims to predict housing prices based on various features from the California Housing Prices dataset using a Random Forest model. The application is built with a modular and scalable architecture and is containerized using Docker. The prediction model is served via a REST API using FastAPI.

Table of Contents
Project Overview
Software Architecture
Setup and Installation
Running with Docker
Running Locally Without Docker
API Endpoints
Modeling
Feature Importance
Deployment
Contributing
License
Project Overview
The goal of this project is to predict housing prices in California using features such as median income, housing age, total rooms, and location proximity to the ocean. The model used is a Random Forest Regressor, which has been selected based on performance evaluation against other models like Linear Regression and Gradient Boosting.

Software Architecture
The project is organized into several modules:

Modeling: This module handles training, evaluation, and saving of the machine learning models.
Data Processing: Handles preprocessing tasks such as scaling, encoding categorical variables, and handling missing values.
Model Inference: Loads the pre-trained Random Forest model and handles predictions.
Error Handling: Manages exceptions and provides graceful error messages.
REST API: A FastAPI-based service that exposes endpoints for making predictions.
The application is containerized using Docker to ensure consistent deployment across different environments.

Setup and Installation
Running with Docker
Clone the repository:

bash
Copy code
git clone https://github.com/your-username/housing-price-prediction.git
cd housing-price-prediction
Build the Docker image:

bash
Copy code
docker build -t housing-price-prediction .
Run the Docker container:

bash
Copy code
docker run -d -p 8000:8000 housing-price-prediction
Access the API:
Open your web browser and navigate to http://127.0.0.1:8000.

Running Locally Without Docker
Clone the repository:

bash
Copy code
git clone https://github.com/your-username/housing-price-prediction.git
cd housing-price-prediction
Install the required dependencies:

bash
Copy code
pip install -r requirements.txt
Run the FastAPI application:

bash
Copy code
uvicorn app.main:app --reload
Access the API:
Open your web browser and navigate to http://127.0.0.1:8000.

API Endpoints
POST /predict/: Accepts JSON input of housing features and returns the predicted housing price.
Example request:
json
Copy code
{
  "longitude": -122.23,
  "latitude": 37.88,
  "housingMedianAge": 41,
  "totalRooms": 880,
  "totalBedrooms": 129,
  "population": 322,
  "households": 126,
  "medianIncome": 8.3252,
  "oceanProximity": "NEAR BAY"
}
Example response:
json
Copy code
{
  "predicted_price": 452600.0
}
Modeling
The Random Forest Regressor was chosen after comparing its performance with other models such as Linear Regression and Gradient Boosting Regressor. The model was trained on the California Housing Prices dataset, and feature importance was analyzed to understand the contribution of each feature.

Feature Importance
The following features were identified as most important in predicting housing prices:

Median Income
Latitude
Longitude
Total Rooms
The feature_importance.png plot in the repository visualizes the importance of each feature.

Deployment
The application is containerized using Docker for consistent deployment across environments. It can be run locally or deployed on cloud platforms that support Docker containers.

Contributing
Contributions are welcome! If you have any suggestions or improvements, feel free to fork the repository and submit a pull request.

License
This project is licensed under the MIT License. See the LICENSE file for more details.