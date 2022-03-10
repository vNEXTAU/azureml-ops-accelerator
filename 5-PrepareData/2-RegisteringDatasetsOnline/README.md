---
sort: 2
---

# Registering Data to AML
<!-- Before connecting your dataset with AML services for training, it is required to convert your datasets into [Azure Dataset class](https://docs.microsoft.com/en-us/python/api/azureml-core/azureml.core.dataset(class)?view=azure-ml-py) and register it within AML. The best practice of managing your datasets is to store the dataset connection information within a [Azure Datastore](https://docs.microsoft.com/en-us/python/api/azureml-core/azureml.core.datastore.datastore?view=azure-ml-py) securely. -->
<!-- [Creating data store and dataset](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-connect-data-ui?tabs=credential#create-datastores) -->
Source: [Connect to data with the Azure Machine Learning studio](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-connect-data-ui?tabs=credential)

Connect to your data in storage services on Azure with Azure Machine Learning datastores, and then package that data for tasks in your ML workflows with Azure Machine Learning datasets.


## Creating AML Dataset
Source: [Create Azure Machine Learning datasets](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-create-register-datasets)

By creating a dataset, you create a reference to the data source location, along with a copy of its metadata. 
Because the data remains in its existing location, you incur no extra storage cost, and don't risk the integrity of your data sources. 
Also datasets are lazily evaluated, which aids in workflow performance speeds. You can create datasets from datastores, public URLs, and [Azure Open Datasets](https://docs.microsoft.com/en-us/azure/open-datasets/how-to-create-azure-machine-learning-dataset-from-open-dataset).

With datasets you can,
* Access data during model training.
* Share data and collaborate with other users.
* Leverage open-source libraries, like pandas, for data exploration.
* Because datasets are lazily evaluated, and the data remains in its existing location, you
    * Keep a single copy of data in your storage.
    * Incur no extra storage cost
    * Don't risk unintentionally changing your original data sources.
    * Improve ML workflow performance speeds.

More details of creating a Azure Machine learning datasets [here](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-create-register-datasets#create-datasets-from-datastores).

## Create AML Datastore 
Source: [Connect to storage services on Azure with datastores](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-access-data)

For the data to be accessible by Azure Machine Learning, datasets must be created from paths in Azure Machine Learning datastores or web URLs.

Securely connect to your storage service on Azure, by storing your connection information, like your subscription ID and token authorization in your Key Vault associated with the workspace.
Because your information is securely stored, you
* Don't put authentication credentials or original data sources at risk.
* No longer need to hard code them in your scripts.

## Register datasets
To complete the creation process, register your datasets with a workspace. Use the register() method to register datasets with your workspace in order to share them with others and reuse them across experiments in your workspace:
```python
titanic_ds = titanic_ds.register(workspace=workspace,
                                 name='titanic_ds',
                                 description='titanic training data')
```

Alternatively, it is also possible to register and upload your datasets directly to the data store that you have created:
```python
from azureml.core import Workspace, Datastore, Dataset
import pandas as pd

pandas_df = pd.read_csv('<path to your csv file>')
ws = Workspace.from_config()
datastore = Datastore.get(ws, '<name of your datastore>')
dataset = Dataset.Tabular.register_pandas_dataframe(pandas_df, datastore, "dataset_from_pandas_df", show_progress=True)
```

## Secure access to datasets
Source: [Secure data access in Azure Machine Learning](https://docs.microsoft.com/en-us/azure/machine-learning/concept-data#data-workflow)

To ensure you securely connect to your Azure storage service, Azure Machine Learning requires that you have permission to access the corresponding data storage. This access depends on the authentication credentials used to register the datastore.

Azure Machine Learning makes it easy to connect to your data in the cloud. It provides an abstraction layer over the underlying storage service, so you can securely access and work with your data without having to write code specific to your storage type. Azure Machine Learning also provides the following data capabilities:

* Interoperability with Pandas and Spark DataFrames
* Versioning and tracking of data lineage
* Data labeling
* Data drift monitoring






