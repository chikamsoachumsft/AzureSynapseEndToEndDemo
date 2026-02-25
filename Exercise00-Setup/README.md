## Exercise 00 - Setup: Deploy Azure Synapse Demo in Your Azure Environment

### Objective

Deploy a full Azure Synapse Analytics workspace with Dedicated SQL Pool, Spark Pool, and all required pipeline artifacts in a single step. You will also configure the linked service for your storage account and copy the health care sample dataset to your Azure Data Lake.

### Prerequisites

- A [GitHub account](https://github.com/) with a fork of this repository.
- An active [Azure subscription](https://azure.microsoft.com/free/) with Contributor or Owner role.

### Deployment Steps
Please follow the below steps to successfully deploy a Synapse workspace and its artifacts on your Azure subscription

* Fork microsoft/AzureSynapseEndToEndDemo project to your local github account. Make sure to check "Copy the main branch only".

    ![Animated GIF showing how to fork the AzureSynapseEndToEndDemo repository on GitHub and copy only the main branch](/Images/Forking.gif)

* Once you fork the AzureSynapseEndToEndDemo project to your github account, please click on **Deploy to Azure** button to start the deployment

    [![Deploy To Azure](/Images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmicrosoft%2FAzureSynapseEndToEndDemo%2Fmain%2FARMTemplate%2Fazuredeploy.json)

* **Deploy to Azure** button takes you to the https://ms.portal.azure.com/#create/Microsoft.Template webpage. Please provide subscription, resource group, region, storage account name, storage container name, workspace name, dedicated sql pool name, spark pool name, spark pool node size, sql administration username/password, sku (dedicated sql pool Data Warehouse Units), and github username parameter values.

    >:exclamation::point_right:**It's incredibly important that you write down all the values in the above step. Many will need to be supplied later as parameters.**

    >*Note: The github username should be the target github account where you forked the project. Example: If https://github.com/JohnDoe/AzureSynapseEndToEndDemo is the github project url, then "JohnDoe" is github account name.*

* Click on the **Review + Create** button to trigger deployment validation. If deployment validation is successful, the single click deployment will deploy a Synapse Workspace, Dedicated SQL Pool, and Spark Pool. This deployment also enables git configuration so all the required artifacts for the end-to-end demo are committed to your user github project. This completes the Azure Synapse end-to-end code deployment step.

    >*Note: If deployment is incomplete, please look at the resource group activity log and find the latest deployment errors for more information*

### Demo Setup

First you will need to fill in a parameter before you can complete the exercises.  We need to provide the linked service to your storage account with the storage account name you chose during deployment.

![Azure Synapse Studio showing the linked service list with the storage account linked service highlighted](https://user-images.githubusercontent.com/59613090/192065803-c1c7ccd8-0ab5-487f-aeca-0bb957d9e24e.png)


Once you click on the linked service name it will open a panel where we can make changes and provide the correct parameter for our storage account.

![Panel showing the linked service configuration where you enter your storage account name as a parameter](https://user-images.githubusercontent.com/59613090/192065892-d103a4b9-dffb-4198-8036-28ab4045382a.png)


Now that the parameter is complete you'll need to copy the demo data from our Microsoft repository to your data lake.  The data used in these exercises is synthetic health care data generated from [Synthea](https://synthea.mitre.org/) using their [Data Generator](https://github.com/synthetichealth/synthea/wiki/Basic-Setup-and-Running) and is all open source.  Alternatively, you could generate the data yourself and copy it to your lake.  To begin the copy you need to open the Data Prep Pipeline.

![Azure Synapse Studio Integrate hub showing the Data Prep Pipeline selected in the pipeline list](https://user-images.githubusercontent.com/59613090/192581982-60376d3f-201c-4416-bd9e-57f41c81f285.png)


Once you have the pipeline open, you can execute it by clicking debug.  When you click debug a flyout panel will open on the right side asking for two runtime parameters.  First is the name of the storage account you chose during deployment and the second has the default value of '1tb'.  You have a choice between two data source sizes and can choose either '1tb' or '30tb'. If you stick with the '1tb' default you can always go back later, run the pipeline again choosing '30tb' and copy that to your data lake as well.

![Debug flyout panel showing the StorageName runtime parameter field for the Data Prep Pipeline](https://user-images.githubusercontent.com/59613090/193362543-5b3cc7a2-59a4-44cb-a40c-99d5e90d75b9.png)

![Debug flyout panel showing the DatasetSize parameter with the default value of 1tb selected](https://user-images.githubusercontent.com/59613090/193361209-7b9ba056-d7b4-4415-baeb-6b7f012b1d47.png)


### Validation

Once the Data Prep Pipeline run completes successfully, verify the setup is complete:

- In **Azure Synapse Studio**, go to the **Data** hub and expand your storage account.
- Confirm that the `raw` container contains the FHIR health care data files copied from the Microsoft repository.
- Confirm that the Synapse workspace, Dedicated SQL Pool, and Spark Pool appear in the **Manage** hub under their respective tabs.

## Congratulations on completing setup. You are now ready to move to [Exercise 01 - Claims](/Exercise01-Claims/README.md)
