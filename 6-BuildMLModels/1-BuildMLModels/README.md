---
sort: 1
---
# Building Machine Learning Models
Source: [Train models with Azure Machine Learning](https://docs.microsoft.com/en-us/azure/machine-learning/concept-train-machine-learning-model)

Azure Machine Learning provides several ways to train your models, from code-first solutions using the SDK to low-code solutions such as automated machine learning and the visual designer. Use the following list to determine which training method is right for you:

* [**Azure Machine Learning SDK for Python**](https://docs.microsoft.com/en-us/python/api/overview/azure/ml/?view=azure-ml-py): The Python SDK provides several ways to train models, each with different capabilities.
  * ***Run configuration*** - A typical way to train models is to use a training script and run configuration. The run configuration provides the information needed to configure the training environment used to train your model. You can specify your training script, compute target, and Azure ML environment in your run configuration and run a training job.
  * ***Automated machine learning*** - Automated machine learning allows you to train models without extensive data science or programming knowledge. For people with a data science and programming background, it provides a way to save time and resources by automating algorithm selection and hyperparameter tuning. You don't have to worry about defining a run configuration when using automated machine learning.
  * ***Machine learning pipeline*** - Pipelines are not a different training method, but a way of defining a workflow using modular, reusable steps, that can include training as part of the workflow. Machine learning pipelines support using automated machine learning and run configuration to train models. Since pipelines are not focused specifically on training, the reasons for using a pipeline are more varied than the other training methods. Generally, you might use a pipeline when:
    * You want to schedule unattended processes such as long running training jobs or data preparation.
    * Use multiple steps that are coordinated across heterogeneous compute resources and storage locations.
    * Use the pipeline as a reusable template for specific scenarios, such as retraining or batch scoring.
    * Track and version data sources, inputs, and outputs for your workflow.
    * Your workflow is implemented by different teams that work on specific steps independently. Steps can then be joined together in a pipeline to implement the workflow.
* [**Azure Machine Learning designer**](https://docs.microsoft.com/en-us/azure/machine-learning/concept-designer): Azure Machine Learning designer provides an easy entry-point into machine learning for building proof of concepts, or for users with little coding experience. It allows you to train models using a drag and drop web-based UI. You can use Python code as part of the design, or train models without writing any code.
* [**Azure CLI**](https://docs.microsoft.com/en-us/azure/machine-learning/reference-azure-machine-learning-cli): The machine learning CLI provides commands for common tasks with Azure Machine Learning, and is often used for scripting and automating tasks. For example, once you've created a training script or pipeline, you might use the Azure CLI to start a training run on a schedule or when the data files used for training are updated. For training models, it provides commands that submit training jobs. It can submit jobs using run configurations or pipelines.
  

## Training Machine Learning Models
Source: [Configure and submit training runs](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-set-up-training-targets)

When training, it is common to start on your local computer, and then later scale out to a cloud-based cluster. With Azure Machine Learning, you can run your script on various compute targets without having to change your training script.

All you need to do is define the environment for each compute target within a script run configuration. Then, when you want to run your training experiment on a different compute target, specify the run configuration for that compute.

The code pattern to submit a training run is the same for all types of compute targets:

1. Create an [experiment](https://docs.microsoft.com/en-us/azure/machine-learning/concept-azure-machine-learning-architecture#experiments) to run
2. Create an [environment](https://docs.microsoft.com/en-us/azure/machine-learning/concept-environments) where the script will run
3. Create a [ScriptRunConfig](https://docs.microsoft.com/en-us/python/api/azureml-core/azureml.core.scriptrunconfig?view=azure-ml-py), which specifies the compute target and environment   
   * A ScriptRunConfig is used to configure the information necessary for submitting a training run as part of an experiment.
4. Submit the [run](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-set-up-training-targets#submit-the-experiment)
5. Wait for the run to complete and save the model.

## Deploying Machine Learning Model
Source: [Deploy machine learning models to Azure](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-deploy-and-where?tabs=azcli)

<!-- A typical situation for a deployed machine learning service is that you need the following components:

* Resources representing the specific model that you want deployed (for example: a pytorch model file).
* Code that you will be running in the service, that executes the model on a given input.
  
Azure Machine Learnings allows you to separate the deployment into two separate components, so that you can keep the same code, but merely update the model. We define the mechanism by which you upload a model separately from your code as "registering the model". -->

The workflow is similar no matter where you deploy your model:

1. [Register the model](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-deploy-and-where?tabs=azcli#registermodel).
   
   When you register a model, we upload the model to the cloud (in your workspace's default storage account) and then mount it to the same compute where your webservice is running.
2. [Prepare an entry script](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-deploy-and-where?tabs=azcli#define-a-dummy-entry-script).
   
   The entry script receives data submitted to a deployed web service and passes it to the model. It then returns the model's response to the client. The script is specific to your model. The entry script must understand the data that the model expects and returns.
3. [Prepare an inference configuration](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-deploy-and-where?tabs=azcli#define-an-inference-configuration).
   
   An inference configuration describes the Docker container and files to use when initializing your web service. All of the files within your source directory, including subdirectories, will be zipped up and uploaded to the cloud when you deploy your web service.
4. [Deploy the model locally to ensure everything works](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-deploy-and-where?tabs=azcli#define-a-deployment-configuration).
   
   A deployment configuration specifies the amount of memory and cores your webservice needs in order to run. It also provides configuration details of the underlying webservice. 
5. [Choose a compute target](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-deploy-and-where?tabs=azcli#choose-a-compute-target).
   
   The compute target you use to host your model will affect the cost and availability of your deployed endpoint. 
6. [Deploy the model to the cloud](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-deploy-and-where?tabs=azcli#deploy-to-cloud).
   
   Once you've confirmed your service works locally and chosen a remote compute target, you are ready to deploy to the cloud.
7. [Test the resulting web service](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-deploy-and-where?tabs=azcli#call-your-remote-webservice).
   
   When you deploy remotely, you may need to get your service key in order to make an inference request.
   
For more information on the concepts involved in the machine learning deployment workflow, see [Manage, deploy, and monitor models with Azure Machine Learning](https://docs.microsoft.com/en-us/azure/machine-learning/concept-model-management-and-deployment).

<!-- https://github.com/Azure/azureml-examples/blob/main/notebooks/basics/1.train-lightgbm-local.ipynb -->
