## Registering Data to AML
Before connecting your dataset with AML services for training, it is required to convert your datasets into [Azure Dataset class](https://docs.microsoft.com/en-us/python/api/azureml-core/azureml.core.dataset(class)?view=azure-ml-py) and register it within AML. The best practice of managing your datasets is to store the dataset connection information within a [Azure Datastore](https://docs.microsoft.com/en-us/python/api/azureml-core/azureml.core.datastore.datastore?view=azure-ml-py) securely.
<!-- [Creating data store and dataset](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-connect-data-ui?tabs=credential#create-datastores) -->

### [Creating AML Dataset](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-connect-data-ui?tabs=credential#create-datasets)
By creating a dataset, you create a reference to the data source location, along with a copy of its metadata. 
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

### [Create AML Datastore](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-connect-data-ui?tabs=credential#create-datastores) 
Securely connect to your storage service on Azure, by storing your connection information, like your subscription ID and token authorization in your Key Vault associated with the workspace.
Because your information is securely stored, you
* Don't put authentication credentials or original data sources at risk.
* No longer need to hard code them in your scripts.

### Register dataset (s)
To complete the creation process, register your datasets with a workspace. Use the register() method to register datasets with your workspace in order to share them with others and reuse them across experiments in your workspace:
```python
from azureml.core import Workspace, Datastore, Dataset
import pandas as pd

pandas_df = pd.read_csv('<path to your csv file>')
ws = Workspace.from_config()
datastore = Datastore.get(ws, '<name of your datastore>')
dataset = Dataset.Tabular.register_pandas_dataframe(pandas_df, datastore, "dataset_from_pandas_df", show_progress=True)
```

Alternatively, it is also possible to register and upload your datasets directly to the data store that you have created to enjoy its benefits:
```python
from azureml.core import Workspace, Datastore, Dataset
import pandas as pd

pandas_df = pd.read_csv('<path to your csv file>')
ws = Workspace.from_config()
datastore = Datastore.get(ws, '<name of your datastore>')
dataset = Dataset.Tabular.register_pandas_dataframe(pandas_df, datastore, "dataset_from_pandas_df", show_progress=True)
```

### [Secure access to dataset (s)](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-connect-data-ui?tabs=credential#storage-access-and-permissions)
To ensure you securely connect to your Azure storage service, Azure Machine Learning requires that you have permission to access the corresponding data storage. This access depends on the authentication credentials used to register the datastore.






