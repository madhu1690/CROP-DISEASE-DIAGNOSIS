# FLORA  ~ Potato Disease Classification

This project classifies diseases affecting potatoes using machine learning models, with deployment options for serving predictions via APIs and mobile apps.

## Setup Instructions

### Python Setup

1. **Install Python**
   - Make sure Python 3.x is installed on your system. If not, download and install it from [python.org](https://www.python.org).

2. **Install Python packages**
   ```bash
   pip install -r training/requirements.txt
   pip install -r api/requirements.txt


bash
Copy code
pip install -r training/requirements.txt
pip install -r api/requirements.txt
Tensorflow Serving

Set up Tensorflow Serving as needed.
ReactJS Setup
Install Node.js and NPM

Follow Node.js installation instructions.
Install dependencies

bash
Copy code
cd frontend
npm install
Environment configuration

Copy .env.example to .env and update REACT_APP_API_URL.
React-Native Setup
Set up React Native environment

Follow React Native CLI Quickstart.
Install dependencies

bash
Copy code
cd mobile-app
yarn install
Environment configuration

Copy .env.example to .env and update API URL if necessary.
Training the Model
Prepare and train model
bash
Copy code
jupyter notebook
Open training/potato-disease-training.ipynb.
Update dataset path in cell #2.
Execute all cells to train and save the model in models folder.
Running the API
Using FastAPI
Run FastAPI Server
bash
Copy code
cd api
uvicorn main:app --reload --host 0.0.0.0
Access API at http://0.0.0.0:8000.
Using FastAPI with Tensorflow Serving
Run Tensorflow Serving

bash
Copy code
cd api
docker run -t --rm -p 8501:8501 -v /path/to/potato-disease-classification:/potato-disease-classification tensorflow/serving --rest_api_port=8501 --model_config_file=/potato-disease-classification/models.config
Run FastAPI Server with TF Serving

bash
Copy code
uvicorn main-tf-serving:app --reload --host 0.0.0.0
Access API at http://0.0.0.0:8000.
Running the Frontend
Start frontend
bash
Copy code
cd frontend
npm start
Running the React-Native App
Start mobile app (Android/iOS)
bash
Copy code
cd mobile-app
npm run android
# or
npm run ios
Deploying TF Lite Model on Google Cloud Platform (GCP)
Create GCP account and project

Note project ID.
Upload model to GCP bucket

Upload potatoes.h5 to models/potatoes.h5 in GCP bucket.
Install and authenticate Google Cloud SDK

Deploy TF Lite model

bash
Copy code
cd gcp
gcloud functions deploy predict_lite --runtime python38 --trigger-http --memory 512 --project project_id
Test with Postman using Trigger URL.
Deploying TF Model (.h5) on Google Cloud Platform (GCP)
Set up GCP account and project

Upload .h5 model to GCP bucket

Deploy TF model

bash
Copy code
cd gcp
gcloud functions deploy predict --runtime python38 --trigger-http --memory 512 --project project_id
Test with Postman using Trigger URL.
