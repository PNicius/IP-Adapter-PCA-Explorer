# IP-Adapter Feature Space Explorer

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PNicius/IP-Adapter-PCA-Explorer/blob/main/IP_Adapter_PCA_Exploration_Pipeline.ipynb)

## Description
This repository contains a streamlined pipeline for exploring and manipulating the image embedding latent space in Stable Diffusion. By extracting CLIP image features from a custom dataset of images, this notebook uses Principal Component Analysis (PCA) and UMAP to analyze and visualize the dataset's underlying visual structures. It then allows users to mathematically shift embeddings along specific principal components and feed them back into an IP-Adapter, effectively steering the image generation process based on the extracted concepts.

## Features
* **Feature Extraction:** Automatically processes a folder of images to extract CLIP image embeddings.
* **PCA Training & Variance Analysis:** Identifies the core visual directions of your dataset and generates Scree plots to visualize explained variance.
* **Interactive 3D UMAP Visualization:** Projects complex, high-dimensional image features into an interactive 3D HTML plot for spatial analysis.
* **Latent Space Steering:** Modifies the mean embedding of the dataset along specific PCA components, allowing you to generate novel images that isolate distinct visual styles or concepts from your dataset.
* **Colab-Ready:** Designed to run entirely within Google Colab's temporary environment without requiring Google Drive mounting.

## Getting Started

1. Click the **Open in Colab** badge above to launch the notebook.
2. Run the first cell to install all required dependencies (Diffusers, Transformers, IP-Adapter, UMAP, etc.).
3. Upload your target images into the `/content/dataset/` folder within the Colab file explorer.
4. Run the remaining cells sequentially to extract features, train the PCA model, visualize the data, and generate new images.

## Output
All generated models, charts, and modified images are automatically saved to the `/content/output/` directory for easy downloading. This includes:
* `pca_model.pkl`
* `scree_plot.png` & `pca_directions.png`
* `umap_3d.html` (Interactive plot)
* `experiment_results/` (Generated images)

## Requirements
* `torch`
* `diffusers`
* `transformers`
* `ip_adapter`
* `scikit-learn`
* `umap-learn`
* `plotly`
