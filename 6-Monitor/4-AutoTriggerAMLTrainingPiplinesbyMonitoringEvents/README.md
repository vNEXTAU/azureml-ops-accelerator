---
sort: 4
---
# Auto Trigger AML Workflow in Pipeline
Source: [Trigger machine learning pipelines](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-trigger-published-pipeline)

You can create a schedule based on elapsed time or on file-system changes. Time-based schedules can be used to take care of routine tasks, such as monitoring for data drift. Change-based schedules can be used to react to irregular or unpredictable changes, such as new data being uploaded or old data being edited.


## Auto Trigger with Event Grid
Source: [Trigger applications, processes, or CI/CD workflows based on Azure Machine Learning events (preview)](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-use-event-grid)

Azure Machine Learning manages the entire lifecycle of machine learning process, including model training, model deployment, and monitoring. You can use Event Grid to react to Azure Machine Learning events, such as the completion of training runs, the registration and deployment of models, and the detection of data drift, by using modern serverless architectures. You can then subscribe and consume events such as run status changed, run completion, model registration, model deployment, and data drift detection within a workspace.

When to use Event Grid for event driven actions:

* Send emails on run failure and run completion
* Use an Azure function after a model is registered
* Streaming events from Azure Machine Learning to various of endpoints
* Trigger an ML pipeline when drift is detected

