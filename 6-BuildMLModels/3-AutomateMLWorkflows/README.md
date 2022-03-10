---
sort: 3
---
# Automate Machie Learning Workflows
Source: [What are Azure Machine Learning pipelines?](https://docs.microsoft.com/en-us/azure/machine-learning/concept-ml-pipelines)

You can use a pipeline to automate the machine learning lifecycle. Some of the operations you can automate are:

An Azure Machine Learning pipeline is an independently executable workflow of a complete machine learning task. Subtasks are encapsulated as a series of steps within the pipeline. An Azure Machine Learning pipeline can be as simple as one that calls a Python script, so may do just about anything. Pipelines should focus on machine learning tasks such as:

* Data preparation (extract, transform, load operations)
* Training machine learning models with on-demand scale-out and scale-up
* Deployment of machine learning models as public or private web services
* Monitoring deployed machine learning models (such as for performance or data-drift analysis)

Time-consuming steps can be done only when their input changes. A change to the training script may be run without redoing the data loading and preparation steps. Separate steps can use different compute type/sizes for each steps. Independent steps allow multiple data scientists to work on the same pipeline at the same time without over-taxing compute resources.

To create Azure pipeline, see [Create the pipeline](https://docs.microsoft.com/en-us/azure/devops/pipelines/targets/azure-machine-learning?context=azure%2Fmachine-learning%2Fcontext%2Fml-context&view=azure-devops&tabs=yaml).

To create Azure pipeline with the Azure Machine Learning SDK, see [Create and run machine learning pipelines with Azure Machine Learning SDK](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-create-machine-learning-pipelines?view=azure-devops).

To create with the Azure Machine Learning CLI, see [Create and run machine learning pipelines using components with the Azure Machine Learning CLI (Preview)](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-create-component-pipelines-cli?view=azure-devops).

