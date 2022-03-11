---
sort: 1
---
# Monitor Azure Machine Learning Workflows

## Monitor Machine Learning Model Performance
<<<<<<< HEAD
**Source**: [Start, monitor, and track run history](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-track-monitor-analyze-runs?tabs=python)
=======
Source: [Start, monitor, and track run history](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-track-monitor-analyze-runs?tabs=python)
>>>>>>> 64827816565eb76127a9a3ee632ed86877bd5b0e

The [Azure Machine Learning SDK for Python](https://docs.microsoft.com/en-us/python/api/overview/azure/ml/?view=azure-ml-py), [Machine Learning CLI](https://docs.microsoft.com/en-us/azure/machine-learning/reference-azure-machine-learning-cli), and [Azure Machine Learning studio](https://ml.azure.com/selectWorkspace) provide various methods to monitor, organize, and track your runs for training and experimentation. Your ML run history is an important part of an explainable and repeatable ML development process.

It is possible to log real-time information using both the default Python logging package and Azure Machine Learning Python SDK-specific functionality. You can log locally and send logs to your workspace in the portal.
Logs can help you diagnose errors and warnings, or track performance metrics like parameters and model performance. 
We recommend logging your models, metrics and artifacts with [MLflow](https://mlflow.org/docs/latest/index.html) as it's open source and it supports local mode to cloud portability. 

* MLflow is an open-source library for managing the life cycle of your machine learning experiments. MLflow Tracking is a component of MLflow that logs and tracks your training run metrics and model artifacts, no matter your experiment's environment.

Over the course of an automated ML experiment, many runs are created and each run creates a model. For each model, automated ML generates evaluation metrics and charts that help you measure the model's performance.
Useful evaluation metrics can be found [here](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-understand-automated-ml#classification-metrics).

## Watch for Data Drift

<<<<<<< HEAD
**Source**: [Detect data drift (preview) on datasets](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-monitor-datasets?tabs=python)
=======
Source: [Detect data drift (preview) on datasets](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-monitor-datasets?tabs=python)
>>>>>>> 64827816565eb76127a9a3ee632ed86877bd5b0e

Data drift is one of the top reasons model accuracy degrades over time. For machine learning models, data drift is the change in model input data that leads to model performance degradation. Monitoring data drift helps detect these model performance issues.

Causes of data drift include:

* Upstream process changes, such as a sensor being replaced that changes the units of measurement from inches to centimeters.
* Data quality issues, such as a broken sensor always reading 0.
* Natural drift in the data, such as mean temperature changing with the seasons.
* Change in relation between features, or covariate shift.

Azure Machine Learning simplifies drift detection by computing a single metric abstracting the complexity of datasets being compared. These datasets may have hundreds of features and tens of thousands of rows. Once drift is detected, you drill down into which features are causing the drift. You then inspect feature level metrics to debug and isolate the root cause for the drift.

This top down approach makes it easy to monitor data instead of traditional rules-based techniques. Rules-based techniques such as allowed data range or allowed unique values can be time consuming and error prone.

In Azure Machine Learning, you use dataset monitors to detect and alert for data drift. Dataset monitor is available via either the [Python SDK](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-monitor-datasets?tabs=python#studio-monitor) or [Azure Machine Learning studio](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-monitor-datasets?tabs=azure-studio#studio-monitor).

## Audit Machine Learning Workflows

**Source**: [Audit and manage Azure Machine Learning](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-integrate-azure-policy)

When teams collaborate on Azure Machine Learning, they may face varying requirements to the configuration and organization of resources. Machine learning teams may look for flexibility in how to organize workspaces for collaboration, or size compute clusters to the requirements of their use cases. In these scenarios, it may lead to most productivity if the application team can manage their own infrastructure.

As a platform administrator, you can use policies to lay out guardrails for teams to manage their own resources. [Azure Policy](https://docs.microsoft.com/en-us/azure/governance/policy/) helps audit and govern resource state. Azure Policy is a governance tool that allows you to ensure that Azure resources are compliant with your policies.

Azure Machine Learning provides a set of policies that you can use for common scenarios with Azure Machine Learning. You can assign these policy definitions to your existing subscription or use them as the basis to create your own custom definitions.

For a complete list of the built-in policies for Azure Machine Learning, see [Built-in policies for Azure Machine Learning](https://docs.microsoft.com/en-us/azure/governance/policy/samples/built-in-policies#machine-learning).

To configure built-in policies, see [Configure built-in policies](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-integrate-azure-policy#configure-built-in-policies).

## Auto Trigger AML Workflows in Pipeline
**Source**: [Trigger machine learning pipelines](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-trigger-published-pipeline)

You can create a schedule based on elapsed time or on file-system changes. Time-based schedules can be used to take care of routine tasks, such as monitoring for data drift. Change-based schedules can be used to react to irregular or unpredictable changes, such as new data being uploaded or old data being edited.


### Auto Trigger with Event Grid
**Source**: [Trigger applications, processes, or CI/CD workflows based on Azure Machine Learning events (preview)](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-use-event-grid)

Azure Machine Learning manages the entire lifecycle of machine learning process, including model training, model deployment, and monitoring. You can use Event Grid to react to Azure Machine Learning events, such as the completion of training runs, the registration and deployment of models, and the detection of data drift, by using modern serverless architectures. You can then subscribe and consume events such as run status changed, run completion, model registration, model deployment, and data drift detection within a workspace.

When to use Event Grid for event driven actions:

* Send emails on run failure and run completion
* Use an Azure function after a model is registered
* Streaming events from Azure Machine Learning to various of endpoints
* Trigger an ML pipeline when drift is detected
