# Image-Identification

**[Project Report (Google Doc)](https://docs.google.com/document/d/1GMbW36UGNDOptlfN6k8duxEal2MUcxNH6vINbGsS3RU/edit?usp=sharing)**

This repository provides two approaches for image identification:
- **Exact Image Search**
- **Similar Image Search using Machine Learning**

---

## 📒 Notebooks

- [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/flatneuron/Image-Identification/blob/main/exact_image_search.ipynb) [Exact Image Search Notebook](https://colab.research.google.com/github/flatneuron/Image-Identification/blob/main/exact_image_search.ipynb)
- [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/flatneuron/Image-Identification/blob/main/similarity_search.ipynb) [Similarity Search Notebook](https://colab.research.google.com/github/flatneuron/Image-Identification/blob/main/similarity_search.ipynb)

---

## Approach Summaries

### 1. Exact Image Search
This notebook demonstrates how to efficiently check if an exact match of a given image exists in a database. The approach involves:
- Generating a set of random images (as bit arrays).
- Hashing each image using its byte representation to create a unique identifier.
- Building an index (Python dictionary) mapping image hashes for fast lookup.
- Measuring the time and memory required for generating images, building the index, and querying for an exact match.
- Visualizing performance metrics (generation time, indexing time, query time, and memory usage) as the dataset size increases.

This method is highly efficient for exact matches but does not support finding similar (but not identical) images.

### 2. Similar Image Search (Machine Learning Approach)
This notebook implements a deep learning-based pipeline for finding visually similar images:
- Downloads the COCO-128 dataset using Roboflow.
- Applies SimCLR-style data augmentations to generate different views of each image.
- Defines a custom dataset and a modified ResNet-18 model to produce 128-dimensional embeddings for each image.
- Trains the model using the InfoNCE loss to learn meaningful image representations.
- Computes embeddings for all images and builds a FAISS index for efficient nearest neighbor search.
- Provides a search function to retrieve the top-k most similar images to a query image, and visualizes the results.

This approach enables robust similarity search, even for images that are not exactly the same but share visual features.

---

## 📄 Report
A detailed report describing the methodology, experiments, and results can be found here:
**[Project Report (Google Doc)](https://docs.google.com/document/d/1GMbW36UGNDOptlfN6k8duxEal2MUcxNH6vINbGsS3RU/edit?usp=sharing)**

---

## License
This project is licensed under the MIT License.
