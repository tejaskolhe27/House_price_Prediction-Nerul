## House Price Prediction - Nerul

This project aims to predict house prices in the Nerul area using a machine learning model. The prediction is based on various features such as total square footage, number of bedrooms, number of bathrooms, and location.

### Project Structure
- **server.py:** Python script that sets up a Flask server for handling HTTP requests and responses.

- **utils.py:** Contains utility functions for loading model artifacts, getting location names, and estimating house prices.

- **p1.ipynb:** A Jupyter notebook (or Python script) where the machine learning model is trained and saved. This file is used to preprocess the data, train the model, and save the trained model and necessary artifacts.

- **artifacts/:** Folder containing saved artifacts, such as the trained machine learning model (p1_model.pickle) and the list of data columns (columns.json).

- **neruldata.csv:** Raw dataset containing information about house listings in the Nerul area.

- **cleaneddata.csv:** Cleaned dataset obtained after preprocessing the raw data.

### Setup and Installation
**1. Clone the Repository:**

```
git clone <repository-url>
cd <repository-name>

```

**2. Install Dependencies:** 

```pip install -r requirements.txt```



**3.Run the Flask Server:**

```python server.py```

The server will be accessible at **http://localhost:5000/**

### API Endpoints
**1. Get Location Names:**

- Endpoint: **/get_location_names**
- Method: GET
- Returns a list of available locations for house prediction.
**2. Predict Home Price:**

- Endpoint: **/predict_home_price**
- Method: POST
- Requires parameters: total_sqft, location, bhk, bath
- Returns the estimated house price based on the provided parameters.

### Usage Example
```
# Python code example for using the API
import requests

url = "http://localhost:5000/predict_home_price"
data = {
    "total_sqft": 1000,
    "location": "Sector 21, Nerul, Navi Mumbai",
    "bhk": 3,
    "bath": 3
}

response = requests.post(url, data=data)
result = response.json()

print(f"Estimated Price: {result['estimated_price']} Lakh Indian Rupees")
```
Model Training
If you want to retrain the model or make changes to the data preprocessing steps, refer to the p1.ipynb file.