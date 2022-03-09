# Azure ML-Ops Project Accelerator

Guided accelerator consolidating best practice patterns, IaaC and AML code artefacts to provide reference IP to a support a baseline MLOps implementation on Azure leveraging Azure ML that can be delivered in approximately 12 weeks of project scope. 

This repo is designed to be consumed 'documentation led', with the relevant IaaC or implementation code artefacts linked at the appropriate sections. 

Use the Table of Contents below to help you navigate to the section of repo that you are interested in based on your role or the stage of your project. 


|**Stage**|**Tasks &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;**|**Roles**|
| ---------------------| --------------------- | ----------- |
| **1- MLOps Foundation** | Understanding MLOps <br />· [What’s DevOps?](/1-MLOpsFoundations/0-DevOpsOverview/README.md)<br />· [What’s MLOps?](/1-MLOpsFoundations/1-MLOpsOverview/README.md) | Everyone |
| | Understand Maturity Model <br />· Determine org capability level <br />· Culture and Key Principles | Group Manager, Team Lead, Project Lead |
| | Team formation <br />· Skills, Roles, and Responsibilities<br />· Deciding on (agile) Delivery model   | Everyone  |
| | **Deliverables**<br />· Review the checklist |
| **2- Design and Provision Infrastructure** | Design and approve Infrastructure<br />· Understand Key Architecture & A/ML concepts<br />· Technology Choices (Decision Tree)<br />· Review Reference Architecture<br />· Map team Roles to RBAC<br />· Seek approval | Team Lead, Solution Architect |
| |  Configuring Access Control<br />· Secure access to AML with RBAC<br />· Use Custom Roles when required | Solution Architect, Azure Infrastructure Engineer, Team Lead |
| | Security control for Service Infrastructure<br />· Use vNEXT Integrate & Private Link for AML | Solution Architect, Azure Infrastructure Engineer, Team Lead |
| | Infrastructure Costs Control<br />· Set Budgets and spending alerts<br />· AML Cost Optimisation guide| Solution Architect, Azure Infrastructure Administrator, Team Lead |
| |  **Deliverables**<br />· Approved Solution Design<br />· Review the checklist|
| **3- Deploy Services & Setup Environment**| Accelerate code deployment for Azure ML Services<br />· Automate the deployment of resources<br />· Update the deployment scripts to match the approved Solution Design | Azure Infrastructure Engineer, DevOps Engineer, Team Lead |
| | Setting up local environment for development<br />· Install tools<br />· Connect to AML | Data Scientist, MLOps Engineer, Data Engineer |
| | Organise Azure ML environments | MLOps Engineer, DevOps Engineer |
| | Creating separate environments (Dev, Test, Prod) | MLOps Engineer, DevOps Engineer |
| | **Deliverables**<br />· Full deployed services on Azure using Automated pipelines<br />· Review the checklist |
| **4- Migrate to AML**| Migrate existing ML experiment to Azure ML| MLOps Engineer |
| **5- Prepare data** | Prepare your dataset(s) | Data Engineer, Data Scientist |
| | Registering dataset(s) online<br />· Create AML Datastore<br />· Create AML Experiment<br />· Register datasets<br />· Secure access to datasets | |
| | **Deliverables**<br />· Data is traceable in AML datastores<br />· Review the checklist|
| **6- Build ML models** | Build ML model(s)<br />· Build your ML models locally<br />· Create experiments in AML<br />· Register models in AML along with data, experiment details, etc<br /><br />Validate ML Models<br />· Unit / Integration test ML model<br />· Audit model integrity<br /><br />Train ML models<br />· Create AML pipelines to auto train models<br />· Automate the deployment of AML pipelines<br /><br />Deploy ML models | Data Scientist, Data Engineer, MLOps Engineer, DevOps Engineer |
| |**Deliverables**<br />· Models are versioned and recorded in AML<br />· Review the checklist  |
| **7- Monitoring** | Monitor model performances | MLOps Engineer, DevOps Engineer                                |
|| Watch for data drifts | MLOps Engineer, DevOps Engineer, Data Engineer |
|| Audit machine learning workflows | MLOps Engineer, DevOps Engineer |
| | Auto-trigger AML training pipelines by Monitoring events | MLOps Engineer, DevOps Engineer, Data Engineer  |
| | **Deliverables**<br />· Review the checklist |









## Contributing 

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft 
trademarks or logos is subject to and must follow 
[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general).
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.
