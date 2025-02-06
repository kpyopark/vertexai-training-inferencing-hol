# Unsloth Workshop: Gemma Model Fine-Tuning and Deployment on Vertex AI

This repository provides materials for a workshop focused on fine-tuning the Gemma model using Unsloth and deploying it on Vertex AI. The workshop covers the entire process, from environment setup and data preparation to model training, evaluation, and deployment.

## Repository Contents

*   **./1.unsloth\_training**: Contains notebooks for fine-tuning the Gemma model using the Unsloth library.
    *   **1-1.L4\_Workshop\_renewal.ipynb**: This notebook guides you through the process of setting up the environment, loading the dataset, and fine-tuning the Gemma model using LoRA.
    *   **1-2.L4\_Workshop\_local\_PEFT\_loading.ipynb**:  Demonstrates how to load and test the fine-tuned model locally.
*   **./2.service\_image**: Includes files required to build a Docker image for model serving.
    *   **L4\_Workshop\_image\_making.ipynb**: This notebook explains how to create a Docker image for deploying the fine-tuned model on Vertex AI. It also provides steps for testing the deployed image.
*   **./3.custom\_job\_training**: Placeholder for future custom job training notebooks. Currently empty.
    *   **L4Workshop\_custom\_job\_training.ipynb**: This notebook is currently empty.
*   **main.py**: The main application code for serving the fine-tuned model using FastAPI. It includes functionalities for downloading the model from Google Cloud Storage (GCS), loading the model, and handling prediction requests.
*   **requirements.txt**: Lists the Python dependencies required to run the application.
*   **Dockerfile**: Defines the steps to build a Docker image for the application, including installing system dependencies, setting up the environment, and copying the application code.

## Setup and Usage

### 1. Fine-Tuning the Gemma Model

*   Use the `1-1.L4_Workshop_renewal.ipynb` notebook in the `./1.unsloth_training` directory to fine-tune the Gemma model. This notebook will guide you through setting up the environment, loading the dataset, and fine-tuning the model using LoRA.

### 2. Creating the Docker Image

*   Follow the instructions in the `L4_Workshop_image_making.ipynb` notebook in the `./2.service_image` directory to build a Docker image for deploying the fine-tuned model on Vertex AI.
*   The `Dockerfile`, `requirements.txt`, and `main.py` files are used to build the serving image.  The notebook provides the commands to build and test the image.

### 3. Deploying to Vertex AI

*   The `L4_Workshop_image_making.ipynb` notebook contains instructions for uploading the Docker image to Google Artifact Registry, registering the model in Vertex AI, and deploying it to an endpoint.

## Key Concepts

*   **Unsloth:** A library designed to simplify and optimize the fine-tuning of large language models.
*   **LoRA (Low-Rank Adaptation):** A technique to reduce the number of trainable parameters during fine-tuning by learning low-rank matrices.
*   **Vertex AI:** Google Cloud's machine learning platform for training, deploying, and managing ML models.
*   **Docker:** A platform for building, shipping, and running applications in containers.
*   **FastAPI:** A modern, fast (high-performance), web framework for building APIs with Python.

## Notes

*   Ensure that you have the necessary Google Cloud permissions to create and manage resources in Vertex AI and Google Cloud Storage.
*   The `AIP_STORAGE_URI` environment variable in `main.py` should be set to the correct GCS path where your fine-tuned model is stored.
*   The workshop assumes a basic understanding of machine learning concepts, PyTorch, and cloud computing.
