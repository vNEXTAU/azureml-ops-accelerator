---
sort: 1
---
# Monitor Azure Machine Learning

## Monitor Machine Learning Model Performance
Source: [Start, monitor, and track run history](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-track-monitor-analyze-runs?tabs=python)

The [Azure Machine Learning SDK for Python](https://docs.microsoft.com/en-us/python/api/overview/azure/ml/?view=azure-ml-py), [Machine Learning CLI](https://docs.microsoft.com/en-us/azure/machine-learning/reference-azure-machine-learning-cli), and [Azure Machine Learning studio](https://ml.azure.com/selectWorkspace) provide various methods to monitor, organize, and track your runs for training and experimentation. Your ML run history is an important part of an explainable and repeatable ML development process.

It is possible to log real-time information using both the default Python logging package and Azure Machine Learning Python SDK-specific functionality. You can log locally and send logs to your workspace in the portal.
Logs can help you diagnose errors and warnings, or track performance metrics like parameters and model performance. 
We recommend logging your models, metrics and artifacts with [MLflow](https://mlflow.org/docs/latest/index.html) as it's open source and it supports local mode to cloud portability. 

* MLflow is an open-source library for managing the life cycle of your machine learning experiments. MLflow Tracking is a component of MLflow that logs and tracks your training run metrics and model artifacts, no matter your experiment's environment.

Over the course of an automated ML experiment, many runs are created and each run creates a model. For each model, automated ML generates evaluation metrics and charts that help you measure the model's performance.
Useful evaluation metrics can be found [here](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-understand-automated-ml#classification-metrics).

