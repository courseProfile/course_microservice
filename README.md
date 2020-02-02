[![CircleCI](https://circleci.com/gh/andresaaap/Operationalize-a-Machine-Learning-Microservice-API.svg?style=svg)](https://circleci.com/gh/andresaaap/Operationalize-a-Machine-Learning-Microservice-API)

# Cloud DevOps, Scaling Microservices

The project's goal is to put in production a machine learning microservice using kubernetes with docker and circleci to check how clean is the code.

The service is an API that predict a house price, that API its was did in flask. 

### Install

To start with the API you need to install:

- Docker
- Minikube

### Files explanation
- config.yml: CircleCI configuration file for running the tests
- app.py: Python flask app
- Dockerfile: Dockerfile for building the docker image
- make_prediction.sh: Send a request to the API to get a prediction, in a local environment
- Makefile: includes instructions on environment setup and lint tests
- run_docker.sh: file to deploy a docker container with the app
- run_kubernetes.sh: file to run the app in kubernetes
- upload_docker.sh: file to upload the image to docker hub repository


### Run the project


1. You should have minikube installed. To start a local cluster, type the terminal command: 
```
minikube start --vm-driver=none
```

2. To deploy this application in kubernetes run:
```
./run_kubernetes.sh
```

3. After you’ve called run_kubernetes.sh, you have to check the port exposed by kubernetes and put it in the make_prediction, once that you did, you can execute that file: 
```
./make_prediction.sh
```

4. Delete the cluster
```
minikube delete
```