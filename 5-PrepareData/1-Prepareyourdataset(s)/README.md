## Data Preparation

### Data Ingestion Methods

Before you can prepare datasets in AML you first need to ingest data from different source. Azure Data Factory is used to ingest data and can be used with Azure Machine Learning. Data Factory allows you to easily extract, transform, and load (ETL) data. Once the data has been transformed and loaded into storage, it can be used to train your machine learning models in Azure Machine Learning. 

Simple data transformation can be handled with native Data Factory activities. When it comes to more complicated scenarios, the data can be processed with some custom code. 

Learn how to ingest data with ADF [here](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-data-ingest-adf).

### Data Wrangling

Data wrangling can be achieved in several ways in AML using Compute Instances, Designer, or Synapse Spark Pools.

An [AML Compute Instance](https://docs.microsoft.com/en-us/azure/machine-learning/concept-compute-instance) is a managed cloud-based workstation for data scientists. It is a code first approach to data wrangling. In contrast, [AML Designer](https://docs.microsoft.com/en-us/azure/machine-learning/concept-designer) is a drag-and-drop interface used to train and deploy models in Azure Machine Learning.
Learn why and how to do [data wrangling](https://docs.microsoft.com/en-us/azure/data-factory/wrangling-overview) 
For data wrangling at scale Azure Machine Learning provides [Azure Synapse Analytics integration (preview)](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-data-prep-synapse-spark-pool) which allows you to attach an Apache Spark pool for interactive data exploration and preparation.

### Data Labelling

Data labelling can be administered from Azure Machine Learning to label images or label text data. Use machine-learning-assisted data labelling, or human-in-the-loop labelling, to aid with the task. After labelling, you can create a dataset which can be used to train a model.

Learn how to get started with data labelling projects in AML [here](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-create-labeling-projects).

### Dataset Versioning

[Dataset](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-train-with-datasets) versioning is a way to bookmark the state of your data so that you can apply a specific version of the dataset for future experiments. Typical versioning scenarios include:

- When new data is available for retraining
- When you're applying different data preparation or feature engineering approaches

Learn how to track and version datasets [here](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-version-track-datasets).