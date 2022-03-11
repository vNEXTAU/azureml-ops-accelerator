---
sort: 2
---
# Watch for Data Drift

Source: [Detect data drift (preview) on datasets](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-monitor-datasets?tabs=python)

Data drift is one of the top reasons model accuracy degrades over time. For machine learning models, data drift is the change in model input data that leads to model performance degradation. Monitoring data drift helps detect these model performance issues.

Causes of data drift include:

* Upstream process changes, such as a sensor being replaced that changes the units of measurement from inches to centimeters.
* Data quality issues, such as a broken sensor always reading 0.
* Natural drift in the data, such as mean temperature changing with the seasons.
* Change in relation between features, or covariate shift.

Azure Machine Learning simplifies drift detection by computing a single metric abstracting the complexity of datasets being compared. These datasets may have hundreds of features and tens of thousands of rows. Once drift is detected, you drill down into which features are causing the drift. You then inspect feature level metrics to debug and isolate the root cause for the drift.

This top down approach makes it easy to monitor data instead of traditional rules-based techniques. Rules-based techniques such as allowed data range or allowed unique values can be time consuming and error prone.

In Azure Machine Learning, you use dataset monitors to detect and alert for data drift. Dataset monitor is available via either the [Python SDK](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-monitor-datasets?tabs=python#studio-monitor) or [Azure Machine Learning studio](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-monitor-datasets?tabs=azure-studio#studio-monitor).