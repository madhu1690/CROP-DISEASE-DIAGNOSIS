# CROP DISEASE DIAGNOSIS
## Project Flow:
![My first design](https://github.com/madhu1690/Flora/assets/135344672/c9b28ab8-415c-465c-bb15-71642f11f391)


## Setup for Python:
1. Install Python (Setup instructions)

2. Install Python packages

3. Install Tensorflow Serving (Setup instructions)
## Setup for ReactJS
1. Install Nodejs (Setup instructions)
2. Install NPM (Setup instructions)
3. Install dependencies
4. Copy .env.example as .env.

5. Change API url in .env.

## Setup for React-Native app
1. Go to the React Native environment setup, then select React Native CLI Quickstart tab.

2. Install dependencies

3. Copy .env.example as .env.

4. Change API url in .env.

## Training the Model
1. Download the data from kaggle.
2. Only keep folders related to Potatoes.
3. Run Jupyter Notebook in Browser.
4. Open training/potato-disease-training.ipynb in Jupyter Notebook.
5. In cell #2, update the path to dataset.
6. Run all the Cells one by one.
7. Copy the model generated and save it with the version number in the models folder.
## Running the API
### Using FastAPI
1. Get inside api folder
2. Run the FastAPI Server using uvicorn
uvicorn main:app --reload --host 0.0.0.0
3. Your API is now running at 0.0.0.0:8000
### Using FastAPI & TF Serve
1. Get inside api folder
cd api
2. Copy the models.config.example as models.config and update the paths in file.
3. Run the TF Serve (Update config file path below)
docker run -t --rm -p 8501:8501 -v C:/Code/potato-disease-classification:/potato-disease-classification tensorflow/serving --rest_api_port=8501 --model_config_file=/potato-disease-classification/models.config
4. Run the FastAPI Server using uvicorn For this you can directly run it from your main.py or main-tf-serving.py using pycharm run option (as shown in the video tutorial) OR you can run it from command prompt as shown below,
uvicorn main-tf-serving:app --reload --host 0.0.0.0
5. Your API is now running at 0.0.0.0:8000
## Running the Frontend
1. Get inside api folder
2. Copy the .env.example as .env and update REACT_APP_API_URL to API URL if needed.
3. Run the frontend
## Running the app
1. Get inside mobile-app folder
2. Copy the .env.example as .env and update URL to API URL if needed.
3. Run the app
4. Creating public (signed APK)
## Creating the TF Lite Model
1. Run Jupyter Notebook in Browser.
2. Open training/tf-lite-converter.ipynb in Jupyter Notebook.
3. In cell #2, update the path to dataset.
4. Run all the Cells one by one.
5. Model would be saved in tf-lite-models folder.
## Deploying the TF Lite on GCP
1. Create a GCP account.
2. Create a Project on GCP (Keep note of the project id).
3. Create a GCP bucket.
4. Upload the potatoes.h5 model in the bucket in the path models/potatos.h5.
5. Install Google Cloud SDK (Setup instructions).
6. Authenticate with Google Cloud SDK.
7. Run the deployment script.
8. Your model is now deployed.
9.Use Postman to test the GCF using the Trigger URL.

## Deploying the TF Model (.h5) on GCP
1. Create a GCP account.
2. Create a Project on GCP (Keep note of the project id).
3. Create a GCP bucket.
4. Upload the tf .h5 model generate in the bucket in the path models/potato-model.h5.
5. Install Google Cloud SDK (Setup instructions).
6. Authenticate with Google Cloud SDK.
7. Run the deployment script.
8. Your model is now deployed.
9. Use Postman to test the GCF using the Trigger URL.


