# End-to-End Kidney Disease Classification Deep Learning Project
Welcome to the repository for the End-to-End Kidney Disease Classification Deep Learning Project. This project demonstrates the implementation of a comprehensive machine learning pipeline for kidney disease classification, including model training, evaluation, and deployment using MLOps tools such as MLflow and DVC.

![kidney](https://github.com/ganeshmore99/Kidney-Disease-Classification-Deep-Learning-Project/assets/85934803/227e27d6-c0de-41e8-9643-8776a642d954)


## Table of Contents
#### Introduction
#### GitHub Repository Setup
#### Project Template Creation
#### Project Setup and Requirements Installation
#### Logging, Utils, and Exceptions Modules
#### Project Workflows
#### Notebook Experimentation
#### Modular Code Implementation
#### Training Pipeline
#### MLOps Tools Implementation
#### DVC for Pipeline Tracking
#### Prediction Pipeline and User App Creation
#### Docker
#### GitHub Actions
#### Final CI/CD Deployment on AWS Cloud
#### Conclusion
#### License
#### Acknowledgments

## Introduction
This project aims to classify kidney disease using deep learning models. The workflow covers the complete machine learning lifecycle from data preprocessing, model training, evaluation, and deployment, ensuring reproducibility and efficient model management using MLOps practices.

## GitHub Repository Setup
Set up the GitHub repository to manage and version control all project files and documents. Create necessary branches for development and production.

## Project Template Creation
### Create a standard project template with the following structure:
```
project_root/
├── data/<br />
├── notebooks/
├── src/
│   ├── components/
│   ├── pipelines/
│   ├── utils/
│   ├── logging/
│   └── exceptions/
├── tests/
├── scripts/
├── Dockerfile
├── .gitignore
├── README.md
└── requirements.txt
```
## Project Setup and Requirements Installation
Set up the project environment and install all necessary dependencies using requirements.txt.

```
pip install -r requirements.txt
```

## Logging, Utils, and Exceptions Modules
Create modules for logging, utilities, and custom exceptions to streamline the development process and enhance debugging.

#### Logging: Set up logging configurations for tracking the progress and issues.
#### Utils: Implement utility functions used across the project.
#### Exceptions: Define custom exception classes for better error handling.

## Project Workflows
Define and document the workflows for data preprocessing, model training, evaluation, and deployment. Ensure each workflow is modular and reusable.

## Notebook Experimentation
Conduct initial experimentation and prototyping using Jupyter notebooks to validate the feasibility of the approach and fine-tune hyperparameters.

## Modular Code Implementation
Refactor the notebook code into modular components to improve code readability, reusability, and maintainability.

## Training Pipeline
Develop the training pipeline, including data ingestion, preprocessing, model training, evaluation, and saving models.

## MLOps Tools Implementation
Use MLflow for experiment tracking, model versioning, and registration.

#### MLflow: Track experiments, log metrics, and manage model versions.

## DVC for Pipeline Tracking
Integrate DVC to manage and track the data pipeline, ensuring reproducibility and version control of datasets and models.

## Prediction Pipeline and User App Creation
Create a prediction pipeline to process new data and generate predictions. Develop a user-friendly application interface for end-users to interact with the model.

## Docker
Containerize the application using Docker to ensure consistency across different environments.
```
# Sample Dockerfile
FROM python:3.8-slim

WORKDIR /app

COPY . .

RUN pip install -r requirements.txt

CMD ["python", "src/app.py"]
```

## GitHub Actions
Set up GitHub Actions for continuous integration and continuous delivery (CI/CD) to automate testing, building, and deployment processes.

## Final CI/CD Deployment on AWS Cloud
Deploy the final application on AWS using CI/CD pipelines to ensure scalability and reliability.

## Workflows

1. Update config.yaml
2. Update secrets.yaml [Optional]
3. Update params.yaml
4. Update the entity
5. Update the configuration manager in src config
6. Update the components
7. Update the pipeline 
8. Update the main.py
9. Update the dvc.yaml
10. app.py


## How to run?
### STEPS:

Clone the repository

```bash
https://github.com/ganeshmore99/Kidney-Disease-Classification-Deep-Learning-Project
```
### STEP 01- Create a conda environment after opening the repository

```bash
conda create -n cnncls python=3.8 -y
```

```bash
conda activate cnncls
```

### STEP 02- install the requirements
```bash
pip install -r requirements.txt
```

```bash
# Finally run the following command
python app.py
```

Now,
```bash
open up you local host and port
```

## MLflow

- [Documentation](https://mlflow.org/docs/latest/index.html)

- [MLflow tutorial](https://youtu.be/qdcHHrsXA48?si=bD5vDS60akNphkem)

##### cmd
- mlflow ui

### dagshub
[dagshub](https://dagshub.com/)

MLFLOW_TRACKING_URI=https://dagshub.com/ganeshmore99/Kidney-Disease-Classification-MLflow-DVC.mlflow \
MLFLOW_TRACKING_USERNAME=ganeshmore99 \
MLFLOW_TRACKING_PASSWORD=6824692c47a369aa6f9eac5b10041d5c8edbcef0 \
python script.py

Run this to export as env variables:

```bash

export MLFLOW_TRACKING_URI=https://dagshub.com/ganeshmore99/Kidney-Disease-Classification-MLflow-DVC.mlflow

export MLFLOW_TRACKING_USERNAME=ganeshmore99 

export MLFLOW_TRACKING_PASSWORD=6824692c47a369aa6f9eac5b10041d5c8edbcef0

```

### DVC cmd

1. dvc init
2. dvc repro
3. dvc dag


## About MLflow & DVC

MLflow

 - Its Production Grade
 - Trace all of your expriements
 - Logging & taging your model


DVC 

 - Its very lite weight for POC only
 - lite weight expriements tracker
 - It can perform Orchestration (Creating Pipelines)



# AWS-CICD-Deployment-with-Github-Actions

## 1. Login to AWS console.

## 2. Create IAM user for deployment

	#with specific access

	1. EC2 access : It is virtual machine

	2. ECR: Elastic Container registry to save your docker image in aws


	#Description: About the deployment

	1. Build docker image of the source code

	2. Push your docker image to ECR

	3. Launch Your EC2 

	4. Pull Your image from ECR in EC2

	5. Lauch your docker image in EC2

	#Policy:

	1. AmazonEC2ContainerRegistryFullAccess

	2. AmazonEC2FullAccess

	
## 3. Create ECR repo to store/save docker image
    - Save the URI: 566373416292.dkr.ecr.us-east-1.amazonaws.com/chicken

	
## 4. Create EC2 machine (Ubuntu) 

## 5. Open EC2 and Install docker in EC2 Machine:
	
	
	#optinal

	sudo apt-get update -y

	sudo apt-get upgrade
	
	#required

	curl -fsSL https://get.docker.com -o get-docker.sh

	sudo sh get-docker.sh

	sudo usermod -aG docker ubuntu

	newgrp docker
	
# 6. Configure EC2 as self-hosted runner:
    setting>actions>runner>new self hosted runner> choose os> then run command one by one


# 7. Setup github secrets:

    AWS_ACCESS_KEY_ID=

    AWS_SECRET_ACCESS_KEY=

    AWS_REGION = us-east-1

    AWS_ECR_LOGIN_URI = demo>>  566373416292.dkr.ecr.ap-south-1.amazonaws.com

    ECR_REPOSITORY_NAME = simple-app


## Conclusion
This project showcases a comprehensive approach to developing and deploying a deep learning model for kidney disease classification. By integrating MLOps tools like MLflow and DVC, we ensure that the model development process is reproducible, scalable, and maintainable. The final deployment on AWS demonstrates the project's readiness for production use.

## License
This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments
Gratitude to the open-source community for providing the tools and resources that made this project possible.
Thanks to the authors of the datasets used in this project.


