# Practical MLOps with Vertex AI: End-to-End Model Deployment Examples

This repository contains a collection of hands-on, production-focused MLOps workflows using **Google Cloud Vertex AI**.  
Each folder demonstrates a different model deployment pattern, ranging from fully custom PyTorch containers to AutoML pipelines and Hugging Face model hosting.

The goal of this project is to provide practical, reproducible examples that illustrate how modern ML systems are trained, packaged, deployed, and served on Vertex AI.

---

## Repository Structure

### `bert_agnews/` — Custom PyTorch BERT Deployment (Custom Container + FastAPI)
This example demonstrates how to deploy a **fine-tuned DistilBERT text classifier** using a **custom prediction container**.

Key features:
- Training a lightweight BERT classifier on a small AG News subset  
- Saving the Hugging Face model locally (offline loading)  
- Custom `inference.py` and FastAPI `server.py`  
- Docker image built with Cloud Build  
- Deployment to Vertex AI Endpoints  
- Real-time predictions via HTTP  

This project shows how to deploy **any PyTorch model** using a custom container.

---

### `imdb_model/` — Deploying a Pretrained Hugging Face Model on Vertex AI
This example focuses on **loading and deploying an existing Hugging Face model** without custom training.

It demonstrates:
- Loading a model directly from Hugging Face  
- Wrapping inference logic for Vertex AI  
- Uploading and deploying through the Vertex Model Registry  
- Sending prediction requests to a live endpoint  

This serves as a quickstart for using Vertex AI with pretrained models.

---

### `dry_beans/` — AutoML Tabular Example
This folder contains an **end-to-end AutoML workflow** using Vertex AI Tabular.

It covers:
- Uploading tabular data to Cloud Storage  
- Creating a Vertex AI Dataset  
- Running AutoML training  
- Evaluating the best model  
- Deploying the AutoML model to an endpoint  

This is ideal for users who want a **no-code / low-code** introduction to Vertex AI model training and deployment.

---

## Session Context

This repository supports the workshop:

**Practical MLOps with Vertex AI: Deploying ML Models**  
DevFest Scotland 2025  
29 November 2025, 2:30–3:30 PM GMT

In the session, participants learned the full MLOps workflow—data preparation, model training, evaluation, packaging, and deployment—using multiple real-world examples.

---

## Requirements

To run these examples, you will need:
- A Google Cloud project  
- Vertex AI API enabled  
- Cloud Build + Artifact Registry enabled (for custom containers)  
- Python 3.9+  
- Access to Google Colab or Vertex AI Workbench  
- Basic familiarity with Python and machine learning  

---

## License

MIT License

---

```mermaid
flowchart TD

    A[bert_agnews] --> A1[Train BERT on AG News]
    A --> A2[Save HF model locally]
    A --> A3[Build Custom Docker Container]
    A --> A4[Deploy to Vertex AI Endpoint]

    B[imdb_model] --> B1[Load Pretrained HuggingFace Model]
    B --> B2[Wrap Inference Code]
    B --> B3[Upload to Vertex Model Registry]
    B --> B4[Deploy to Endpoint]

    C[dry_beans] --> C1[Upload Tabular Dataset]
    C --> C2[AutoML Training]
    C --> C3[Evaluate Model]
    C --> C4[Deploy AutoML Model]

    root[Repository] --> A
    root --> B
    root --> C

