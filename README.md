# GKE Deployment Project

This repository contains a Kubernetes-based application designed to be deployed on **Google Kubernetes Engine (GKE)**.

## Project Overview

This project demonstrates how to:

* Deploy containerized applications to **GKE**
* Use Kubernetes manifests (`Deployment`, `Service`, etc.)
* Manage multi-service architecture (API, frontend, model)

The repository serves as a hands-on example of deploying applications in a cloud-native environment using Kubernetes. ([pkg.go.dev][1])

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

---

## 🧠 Notes

* This repository focuses on deployment GKE rather than application development
* Designed for learning cloud-native deployment workflows

---

## Local Development

For local testing and development, this project uses:

* **Minikube**

You can run the application locally before deploying to GKE:

[mnist_Kubernetes](https://github.com/wyccsc/mnist_Kubernetes)

---
