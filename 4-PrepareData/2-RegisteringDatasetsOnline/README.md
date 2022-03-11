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

## Register Datasets
Source: [Import data into Azure Machine Learning designer](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-designer-import-data)

To complete the creation process, register your datasets with a workspace.
You can register existing datasets 
[programatically with the SDK](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-create-register-datasets#datasets-sdk) 
or 
[visually in Azure Machine Learning studio](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-connect-data-ui?tabs=credential#create-datasets).

If the component output data is in a tabular format, you must choose to register the output as a file dataset or tabular dataset.

* [File dataset](https://docs.microsoft.com/en-us/python/api/azureml-core/azureml.data.file_dataset.filedataset?view=azure-ml-py) registers the component's output folder as a file dataset. The output folder contains a data file and meta files that the designer uses internally. Select this option if you want to continue to use the registered dataset in the designer.

* [Tabular dataset](https://docs.microsoft.com/en-us/python/api/azureml-core/azureml.data.tabulardataset?view=azure-ml-py) registers only the component's the output data file as a tabular dataset. This format is easily consumed by other tools, for example in Automated Machine Learning or the Python SDK. Select this option if you plan to use the registered dataset outside of the designer.

## Secure Access to Datasets
Source: [Secure data access in Azure Machine Learning](https://docs.microsoft.com/en-us/azure/machine-learning/concept-data#data-workflow)

To ensure you securely connect to your Azure storage service, Azure Machine Learning requires that you have permission to access the corresponding data storage. This access depends on the authentication credentials used to register the datastore.

Azure Machine Learning makes it easy to connect to your data in the cloud. It provides an abstraction layer over the underlying storage service, so you can securely access and work with your data without having to write code specific to your storage type. Azure Machine Learning also provides the following data capabilities:

* Interoperability with Pandas and Spark DataFrames
* Versioning and tracking of data lineage
* Data labeling
* Data drift monitoring

## Consume Datasets
Source: [Train models with Azure Machine Learning datasets](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-train-with-datasets)

If you have data that are not yet registered as a dataset, use it directly in your training script for your local or remote experiment by *mounting* or *downloading* it to your compute target.

* When you mount a dataset, you attach the files referenced by the dataset to a directory (mount point) and make it available on the compute target. 

* When you download a dataset, all the files referenced by the dataset will be downloaded to the compute target. 

On the other hand, registered datasets are accessible both locally and remotely on compute clusters like the Azure Machine Learning compute. To access your registered dataset across experiments, use the following code to access your workspace and get the dataset that was used in your previously submitted run. By default, the get_by_name() method on the Dataset class returns the latest version of the dataset that's registered with the workspace.



