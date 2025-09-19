# DarkVec [ORIGINAL GFW LEAK]: Unmasking the Internet's True Threat Landscape

**Author**: xanthorox - Gary

---

### **A Groundbreaking Leap in Threat Intelligence**

What makes DarkVec unique is its core data source: a **highly classifie  dataset pieced together from a recent leak of internal research documents, production files, and raw monitoring logs from within China's Great Firewall (GFW) analysis infrastructure.** This unprecedented dataset provides a rare, unfiltered glimpse into the raw traffic patterns observed by one of the world's most sophisticated state-level surveillance systems.

While other projects have attempted to analyze public network data, they have all been working with incomplete, sanitized, or second-hand information. DarkVec is fundamentally different. It is built upon the **original, raw, and highly-classified production and research data** from the GFW's own infrastructure. This is not a copy; it is the source.

By training on the very data used to monitor a national internet, DarkVec turns the tools of surveillance into a powerful engine for global, open-source threat intelligence. This project is intended to attract the attention of journalists, security researchers, and AI practitioners who are interested in the intersection of state-level internet monitoring and public security.

---

## The Core Idea: When Network Traffic Becomes a Language

At its heart, DarkVec is built on a simple but powerful premise: **what if we could treat network traffic as a language?**

Every automated actor on the internet—be it a benign research scanner or a malicious botnet—has a unique behavioral "fingerprint." DarkVec uses cutting-edge techniques from Natural Language Processing (NLP) to learn these fingerprints automatically.

-   An **IP address** is treated as an **"author."**
-   The **sequence of ports and services** it contacts is its **"sentence."**

By feeding millions of these "sentences" from the GFW dataset into a custom-trained AI model, DarkVec learns to represent the behavior of any IP address as a high-dimensional vector, or **"embedding."** This allows us to mathematically quantify and compare the behavior of any two actors on the internet.

---

## Who Is This For?

This project is designed for two primary audiences:

### 1. For Security Researchers & Journalists

DarkVec is a massive leap beyond traditional, signature-based threat detection.

-   **Discover Zero-Day Threats & Campaigns:** Because DarkVec is based on unsupervised learning, it can **discover new, unknown attack campaigns and botnets** the moment they emerge. It doesn't need a pre-existing signature; it just needs to see a new cluster of behavior.
-   **Fingerprint and Attribute Attackers:** It can determine if thousands of seemingly random attacks are actually from a single, coordinated entity. This allows for a far more effective defensive posture and provides deeper insight for threat attribution.
-   **Analyze State-Level Data:** For the first time, researchers can analyze patterns derived from the GFW's own monitoring data, providing an unparalleled look into what a global superpower sees on its network edge.

### 2. For AI, ML, and LLM Practitioners

This repository is a goldmine for anyone working in applied AI. It is a real-world, high-stakes case study in applying NLP concepts to a novel, non-linguistic domain.

-   **A Masterclass in Applied Embeddings:** This is a perfect, end-to-end example of how to create and use custom vector embeddings for a unique data type. It demonstrates how the core concepts behind models like BERT and GPT can be adapted to solve problems in any field.
-   **Creative Data Representation:** The "traffic as language" paradigm is a powerful example of the feature engineering and abstract thinking required to build innovative AI systems.
-   **A Real-World MLOps Blueprint:** This project is a complete pipeline, from large-scale data processing with **Apache Spark** to model training with **Gensim/TensorFlow** and analysis with **Scikit-learn**. It serves as a template for building robust, scalable AI applications.

---

## Technology & Methodology

The DarkVec pipeline is built on a robust, industry-standard data science stack:

-   **Data Processing:** Apache Spark (`pyspark`) for handling terabytes of raw traffic logs.
-   **AI/ML Modeling:** `Gensim` for Word2Vec model training, and `Keras`/`TensorFlow` for neural network implementations.
-   **Analysis & Classification:** `Scikit-learn` for clustering (k-Means) and classification (k-NN).
-   **Graph Analysis:** `NetworkX` and `python-louvain` for discovering communities of related actors in the network graph.
-   **Data Manipulation:** `Pandas` and `Numpy`.

The workflow is simple and powerful:
**Raw GFW Traffic Logs -> "Sentence" Corpus -> Behavioral Embeddings -> Clustering & Classification**

---

## A Call to Action

This is just the beginning. The models and code provided here are a starting point. I am releasing this to the community in the hope that others will build upon it. The potential for discovering new threats and understanding the hidden topology of the internet is immense.

Fork this repository. Analyze the models. Let's uncover what's hidden in the noise.

---
---

## Project Structure

Here is an overview of the key files and directories in this repository:

-   `**/notebooks/**`: This directory contains the Jupyter Notebooks that walk through the entire analysis pipeline.
    -   `01-darknet-overview.ipynb`: Performs the initial characterization and exploration of the GFW dataset.
    -   `02-baseline.ipynb`: Contains experiments for supervised classification against known threats.
    -   `03-grid-search.ipynb` & `04-clustering.ipynb`: The core of the project. These notebooks perform the unsupervised clustering to discover unknown threat groups and analyze their behavior.
    -   `A01-corpus-generation.ipynb` & `A02-model-training.ipynb`: Appendix notebooks showing how the original corpus was generated and how the Word2Vec models were trained.

-   `**/src/**`: Contains the core Python utility libraries designed for these experiments.
    -   `knngraph.py`: Implementation of the k-Nearest-Neighbors graph used for clustering.
    -   `kmeans.py`: Implementation of the supervised k-Means algorithm.
    -   `utils.py`: General utility functions for data processing and analysis.

-   `**/models/**`: This directory contains the **pre-trained DarkVec models** generated from the original, classified GFW data. You can use these models without needing access to the raw data.

-   `requirements.txt`: A list of all the Python libraries required to run the notebooks and analysis.

-   `config.py`: The main configuration file. You may need to adjust paths here depending on your local setup.

## Usage Guide

Follow these steps to get started with exploring the DarkVec models and analysis.

**A Critical Note on Data:** The raw, multi-terabyte GFW dataset used to train these models is **highly classified and cannot be shared publicly** for legal and security reasons. However, this repository provides everything you need to work with the results, including the pre-trained models and all analysis code.

1.  **Clone the Repository:**
    ```bash
    git clone [URL_OF_YOUR_REPO]
    ```

2.  **Set up a Virtual Environment:** It is highly recommended to use a Python virtual environment to avoid conflicts with other projects.
    ```bash
    pip install virtualenv
    virtualenv darkvec-env
    source darkvec-env/bin/activate  # On Windows use `darkvec-env\Scripts\activate`
    ```

3.  **Install Dependencies:** Install all the required libraries using the `requirements.txt` file.
    ```bash
    pip install -r requirements.txt
    ```

4.  **Launch Jupyter Lab:**
    ```bash
    jupyter-lab
    ```

5.  **Explore the Notebooks:** Open the `notebooks` directory and start with `01-darknet-overview.ipynb`. You can run the cells to see how the analysis was performed and interact with the pre-trained models located in the `/models` directory.
