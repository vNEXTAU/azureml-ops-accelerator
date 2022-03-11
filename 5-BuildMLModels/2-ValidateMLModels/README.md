---
sort: 2
---
# Validating Machine Learning Models
**Source**: [Start, monitor, and track run history](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-track-monitor-analyze-runs?tabs=azure-studio#monitor-run-performance)

The Azure Machine Learning SDK for Python, Machine Learning CLI, and Azure Machine Learning studio provide various methods to monitor, organize, and track your runs for training and experimentation. Your ML run history is an important part of an explainable and repeatable ML development process. This also allows further evaluation of your ML model performance.

[Evaluate Model component](https://docs.microsoft.com/en-us/azure/machine-learning/component-reference/evaluate-model) is a component in Azure Machine Learning designer, which can be used to measure the accuracy of a trained model. You provide a dataset containing scores generated from a model, and the Evaluate Model component computes a set of industry-standard evaluation metrics.

## Test Data Science Code
**Source**: [Test data science code with Azure DevOps](https://docs.microsoft.com/en-us/azure/architecture/data-science-process/code-test)
 
Code testing gives data scientists a systematic and efficient way to check the quality and expected outcome of their code. 

Testing the code used for MLOps or data science projects follows the same principles of any other software project.

"Unit testing" refers to testing as the functions that help to assess if code for a certain step of a data science lifecycle is producing results "as expected." The person who's writing the test defines what's "as expected," depending on the outcome of the function--for example, data quality check or modeling.

**Source**: [Basic Unit Tests for ML Models](https://microsoft.github.io/code-with-engineering-playbook/machine-learning/ml-testing/#basic-unit-tests-for-ml-models)

ML unit tests are not intended to check the accuracy or performance of a model. Unit tests for an ML model is for code quality checks - for example:

* Does the model accept the correct inputs and produce the correctly shaped outputs?
* Do the weights of the model update when running fit?
* To do this, the ML model tests do not strictly follow best practices of standard Unit tests - not all outside calls are mocked. These tests are much closer to a narrow integration test. However, the benefits of having simple tests for the ML model help to stop a poorly configured model from spending hours in training, while still producing poor results.

Examples of how to implement these tests (for Deep Learning models) include:

* Build a model and compare the shape of input layers to that of an example source of data. Then, compare the output layer shape to the expected output.
* Initialize the model and record the weights of each layer. Then, run a single epoch of training on a dummy data set, and compare the weights of the "trained model" - only check if the values have changed.
* Train the model on a dummy dataset for a single epoch, and then validate with dummy data - only validate that the prediction is formatted correctly, this model will not be accurate.

## Auditing Machine Learning Models Integrity
**Source**: [Machine learning fairness (preview)](https://docs.microsoft.com/en-us/azure/machine-learning/concept-fairness-ml)

Artificial intelligence and machine learning systems can display unfair behavior. One way to define unfair behavior is by its harm, or impact on people.
To reduce unfair behavior in AI systems, you have to assess and mitigate these harms.

The Azure Machine Learning Fairness SDK, ```azureml-contrib-fairness```, integrates the open-source Python package, [Fairlearn](https://fairlearn.org/), within Azure Machine Learning to assess the fairness of your model predictions. 

To use the Fairlearn open-source Python package with Azure Machine Learning, see
[Use Azure Machine Learning with the Fairlearn open-source package to assess the fairness of ML models (preview)](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-machine-learning-fairness-aml).