# GKE Deployment Project

This repository contains a Kubernetes-based application designed to be deployed on **Google Kubernetes Engine (GKE)**.

## Project Overview

This project demonstrates how to:

* Deploy containerized applications to **GKE**
* Use Kubernetes manifests (`Deployment`, `Service`, etc.)
* Manage multi-service architecture (API, frontend, model)

The repository serves as a hands-on example of deploying applications in a cloud-native environment using Kubernetes.

---

## GKE Deployment

* Images are stored in Google Artifact Registry

* Upload YAML files to Google Cloud Storage

* Connected to cluster

```
gcloud container clusters get-credentials <cluster-name> --region <region>
```

* Proper permissions to pull images from Artifact Registry

```
gcloud projects add-iam-policy-binding PROJECT_ID \
	--member="serviceAccount:$(gcloud projects describe PROJECT_NUMBER \
	--format='value(projectNumber)')-compute@developer.gserviceaccount.com" \
	--role="roles/artifactregistry.reader"
```

* Copy the YAML files to Google Cloud Shell

* Apply the YAML

* Change the external IP for the API service in the frontend service

* Create a new version of the frontend service image

* Update the image tag in the frontend-deployment.yaml file

* Rolling update the frontend deployment

---

## Demo

Video: [Cloud Inference?MNIST on Google Kubernetes Engine](https://youtu.be/KsvLB9mY6ik)

---

## Notes

* This repository focuses on deployment GKE rather than application development
* Designed for learning cloud-native deployment workflows

---

## Local Development

For local testing and development, this project uses:

* **Minikube**

You can run the application locally before deploying to GKE:

Github: [mnist_Kubernetes](https://github.com/wyccsc/mnist_Kubernetes)

## Other

Dataset: [Kaggle Digit Recognizer](https://www.kaggle.com/competitions/digit-recognizer/data)