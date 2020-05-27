[![john4pius](https://circleci.com/gh/john4pius/udacity-project-ml-microservice-kubernetes.svg?style=shield)](https://app.circleci.com/pipelines/github/john4pius/udacity-project-ml-microservice-kubernetes/4/workflows/e7c97cef-0729-4229-8b21-29a9f016bde2)

# Project Overview

The project operationalize machine learning microservice using kubernetes, which is an open-source system for automating the management of containerized applications. Below are the main activities carried out in this project:
* Test your project code using linting
* Complete a Dockerfile to containerize this application
* Deploy your containerized application using Docker and make a prediction
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate that your code has been tested


# Files explanation
* app.py: Python flask app that serves out predictions (inference) about housing prices through API calls
* make_prediction.sh: Send a request to the Python flask app to get a prediction
* Makefile: includes instructions on environment setup and lint tests
* Dockerfile: Dockerfile for building the image
* run_docker.sh: file to be able to get Docker running, locally
* run_kubernetes.sh: file to run the app in kubernetes
* upload_docker.sh: file to upload the image to docker
* config.yml: CircleCI configuration file for running the tests

# Setting up and Building the Project
#### Create and Activate an Environment

```sh
$ python3 -m venv ~/.devops
$ source ~/.devops/bin/activate
```

#### Installing dependencies via project Makefile
```sh
$ make install
```

#### Install VirtualBox:
For MacOS:
```sh
$ brew cask install virtualbox
```
For Windows, I recommend using a Windows host.

#### Install libraries
* Docker
Create a free docker account where you’ll choose a unique username and link your email to a docker account.
Install the latest version of docker, choose the Community Edition (CE) for your operating system, on docker’s installation site.
* Hadolint 
For MacOS
```sh
brew install hadolint
```
For Windows:
```sh
$ scoop install hadolint
```
* Kubernetes (Minikube)
For MacOS:
```sh
$ brew cask install minikube
```
For Windows, I recommend using the Windows installer.

#### Run Lint Checks
```sh
$ make lint
```
#### Run a Container
```sh
$ ./run_docker.sh
```

#### Make a Prediction
```sh
$ ./makeprediction.sh
```

#### Upload the Docker Image
```sh
$ ./upload_docker.sh
```

#### Configure Kubernetes to Run Locally
```sh
$ minikube start
```

#### Deploy with Kubernetes
```sh
$ ./run_kubernetes.sh
```
#### Test using CircleCI. Setup and build project in CircleCI. if your project passes the lint tests, you'll see that the project passes!

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl
