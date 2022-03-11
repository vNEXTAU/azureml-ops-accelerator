---
sort: 1
---

# Data Preparation

## Data Ingestion Methods
Source: [Data ingestion with Azure Data Factory](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-data-ingest-adf)

Before you can prepare datasets in AML you first need to ingest data from different source. [Azure Data Factory](https://docs.microsoft.com/en-us/azure/data-factory/introduction) is used to ingest data and can be used with Azure Machine Learning. Data Factory allows you to easily extract, transform, and load (ETL) data. Once the data has been transformed and loaded into storage, it can be used to train your machine learning models in Azure Machine Learning. 

Simple data transformation can be handled with native Data Factory activities. When it comes to more complicated scenarios, the data can be processed with some custom code. 

<!-- Learn how to ingest data with ADF [here](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-data-ingest-adf). -->

## Data Wrangling

Source: [What is data wrangling?](https://docs.microsoft.com/en-us/azure/data-factory/wrangling-overview)

Organizations need to the ability to explore their critical business data for data preparation and wrangling in order to provide accurate analysis of complex data that continues to grow every day. Data preparation is required so that organizations can use the data in various business processes and reduce the time to value.

Data wrangling can be achieved in several ways in AML using Compute Instances, Designer, or Synapse Spark Pools.

An [AML Compute Instance](https://docs.microsoft.com/en-us/azure/machine-learning/concept-compute-instance) is a managed cloud-based workstation for data scientists. It is a code first approach to data wrangling. 

In contrast, [AML Designer](https://docs.microsoft.com/en-us/azure/machine-learning/concept-designer) is a drag-and-drop interface used to train and deploy models in Azure Machine Learning.

For data wrangling at scale Azure Machine Learning provides [Azure Synapse Analytics integration (preview)](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-data-prep-synapse-spark-pool) which allows you to attach an Apache Spark pool for interactive data exploration and preparation.

## Data Labeling
Source: [Labeling images and text documents](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-label-data)
Data labeling can be administered from Azure Machine Learning to label images or label text data. Use machine-learning-assisted data labelling, or human-in-the-loop labelling, to aid with the task. After labelling, you can create a dataset which can be used to train a model.

Azure Machine Learning data labeling is a central place to create, manage, and monitor data labeling projects:

* Coordinate data, labels, and team members to efficiently manage labeling tasks.
* Tracks progress and maintains the queue of incomplete labeling tasks.
* Start and stop the project and control the labeling progress.
* Review the labeled data and export labeled as an Azure Machine Learning dataset.

After your project administrator creates an i[mage data labeling project](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-create-image-labeling-projects) or [text data labeling project](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-create-text-labeling-projects) in Azure Machine Learning, you can use the labeling tool to rapidly prepare data for a Machine Learning project. 

## Dataset Versioning
Source: [Version and track Azure Machine Learning datasets](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-version-track-datasets)

Dataset versioning is a way to bookmark the state of your data so that you can apply a specific version of the dataset for future experiments. 

Typical versioning scenarios include:
- When new data is available for retraining
- When you're applying different data preparation or feature engineering approaches

When you create a dataset version, you're not creating an extra copy of data with the workspace. Because datasets are references to the data in your storage service, you have a single source of truth, managed by your storage service.

When you load data from a dataset, the current data content referenced by the dataset is always loaded. If you want to make sure that each dataset version is reproducible, we recommend that you not modify data content referenced by the dataset version. 
