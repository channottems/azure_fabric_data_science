# Data Science End-to-End Scenario: Introduction and Architecture

Welcome to the **Data Science End-to-End Scenario** tutorial series! This collection of tutorials guides you through the complete data science lifecycle in **Microsoft Fabric**, from data ingestion and preparation to model training and visualization. By the end of this series, you will have gained hands-on experience in leveraging Microsoft Fabric for building, scoring, and visualizing machine learning models.

You can follow along with the full tutorial on the official Microsoft Learn website:

[**Data Science End-to-End Tutorial**](https://learn.microsoft.com/en-us/fabric/data-science/tutorial-data-science-introduction)

---

## 📚 Table of Contents

1. [Introduction](#-introduction)
2. [Architecture](#-architecture)
3. [Next Steps](#-next-steps)

---

## 🧑‍💻 Introduction

In this tutorial series, you will experience the complete end-to-end data science lifecycle in **Microsoft Fabric**. The process includes:

- **Data ingestion**: Import data from multiple sources into Microsoft Fabric.
- **Data cleaning**: Use Spark and Python-based tools to clean and prepare your data.
- **Data preparation**: Explore and transform data for machine learning models.
- **Model training**: Train and evaluate machine learning models using the Fabric environment.
- **Insight generation**: Score models, generate predictions, and create actionable insights.
- **Visualization**: Use tools like **Power BI** to visualize your insights and share results.

### Data Science Project Lifecycle

A typical data science project includes the following stages:

1. Understand business rules 📊
2. Acquire the data 🌐
3. Explore, clean, prepare, and visualize the data 🔍
4. Train the model and track the experiment 🧠
5. Score the model and generate insights 📈

In this series, you will play the role of a data scientist working with a **churn prediction model** based on a dataset of 10,000 bank customers. Your objective is to predict customer churn and visualize the results.

---

## 🏗️ Architecture

The **Data Science End-to-End Scenario** involves several key components that you will work with throughout this tutorial series:

### Key Components:

1. **Data Sources**:
   - Ingest data from various external data sources, including Azure Data Services, cloud platforms, and on-premises data resources. Fabric supports data ingestion from:
     - Built-in Lakehouses
     - Data Warehouses
     - Semantic Models
     - Apache Spark data sources
     - Various data sources supporting Python tools

   This tutorial focuses on **data ingestion** from a **lakehouse**.

2. **Explore, Clean, and Prepare**:
   - Fabric provides an environment for data exploration, cleaning, and transformation using tools like **Apache Spark** and **Python libraries** such as **Seaborn** and **Data Wrangler**. This tutorial will use **Seaborn** for exploration and **Apache Spark** for data cleaning and preparation.

3. **Models and Experiments**:
   - In **Microsoft Fabric**, you can easily train, evaluate, and track machine learning models. Fabric's **MLflow** integration allows seamless tracking of experiments and model registration. You will:
     - Train machine learning models.
     - Track experiment runs.
     - Register and deploy models for scoring.

4. **Storage**:
   - All data is stored in **Delta Lake** format, allowing for seamless integration across the Fabric environment. This enables Fabric engines to interact with the same dataset stored in the lakehouse. The storage supports both structured and unstructured data and can handle various file formats.

5. **Expose Analysis and Insights**:
   - With **Power BI**, you can visualize data stored in the lakehouse. Microsoft Fabric also supports native visualization libraries in **Python** (e.g., **Matplotlib**, **Seaborn**, **Plotly**) to generate rich visualizations directly from notebooks.

   - **SemPy Library**: Provides built-in visualizations for:
     - Semantic data models
     - Dependency and violation tracking
     - Classification and regression use cases

### Architecture Diagram

Below is an overview of the simplified end-to-end architecture for this data science scenario. The diagram is centered for better visual presentation:

<p align="center">
  <img src="data-science-scenario.png" alt="Data Science End-to-End Architecture" width="80%" />
</p>

---

## ⚡ Next Steps

Now that you've explored the architecture and workflow, it's time to get hands-on with the tutorials! Follow these steps:

1. **Set up your environment** in Microsoft Fabric by creating a workspace and a LakeHouse
2. **Ingest churn data** by following the first notebook or by adding directly to the LakeHouse
3. **Clean and explore**  with the second notebook
4. **Train machine learning models** and track them using **MLflow** with the third notebook
5. **Score the model** and generate insights in the fourth notebook
6. **Bonus: Visualize the results** of your created delta tables in **Power BI**

Each tutorial will walk you through these steps in detail, with code snippets, explanations, and visual aids.

---

## 📜 References

- [What is Microsoft Fabric?](https://learn.microsoft.com/en-us/fabric)
- [MLflow](https://mlflow.org/)
- [Power BI](https://powerbi.microsoft.com/)

---

Thank you for following along with the tutorial series! We hope you enjoy building your data science projects in **Microsoft Fabric**. 😊
