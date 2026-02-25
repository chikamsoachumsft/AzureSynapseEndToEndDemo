# Azure Synapse End-to-End Demo

<img src="https://img.shields.io/github/license/chikamsoachumsft/AzureSynapseEndToEndDemo" alt="MIT License badge">

This repository provides one-click infrastructure and artifact deployment for Azure Synapse Analytics to get you started with Big Data Analytics on a large sized Health Care sample data. You will learn how to ingest, process, and serve large volumes of data using various components of Synapse.

## Reference Architecture

![Architecture diagram showing data flow from ADLS raw storage through Synapse Spark and Dedicated SQL Pool to analytics and visualization](https://user-images.githubusercontent.com/59613090/192642933-23285334-d36c-40e7-8fc1-2e3ed9006ba0.png)

## Features

- **One-click deployment** — Deploy a full Azure Synapse workspace with Dedicated SQL Pool, Spark Pool, and all required artifacts in a single step.
- **Large-scale Health Care sample data** — Uses synthetic health care data (generated via [Synthea](https://synthea.mitre.org/)) at either 1 TB or 30 TB scale.
- **End-to-end data pipelines** — Covers ingestion, transformation, and serving of FHIR-format JSON data using PySpark notebooks, Data Flows, and Copy Activities.
- **Multiple analytics engines** — Demonstrates Dedicated SQL Pool, Synapse Spark, Azure Data Explorer (ADX), and serverless SQL all within one workspace.
- **FHIR data support** — Works with Claims, Observations, and Patients data in FHIR standard format.

## Prerequisites

Before you begin, make sure you have the following:

- A [GitHub account](https://github.com/) — required to fork the repository and enable git integration with Synapse.
- An active [Azure subscription](https://azure.microsoft.com/free/) with permissions to create resource groups and deploy resources.
- Contributor or Owner role on the target Azure subscription or resource group.

## Quick Start

1. **Fork this repository** to your own GitHub account. Make sure to check **Copy the main branch only**.
2. **Deploy to Azure** by clicking the button below. This deploys the Synapse workspace, Dedicated SQL Pool, Spark Pool, and all pipeline artifacts.

   [![Deploy To Azure](Images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmicrosoft%2FAzureSynapseEndToEndDemo%2Fmain%2FARMTemplate%2Fazuredeploy.json)

3. Follow **[Exercise 00 - Setup](Exercise00-Setup/README.md)** to complete the initial configuration and copy the sample data to your data lake.

> :exclamation: **Important:** Write down all parameter values you enter during deployment — many will need to be supplied again in later exercises.

## Exercises

| Exercise | Description |
|----------|-------------|
| [Exercise 00 - Setup](Exercise00-Setup/README.md) | Deploy the Synapse workspace and copy the health care sample data to your Azure Data Lake. |
| [Exercise 01 - Claims](Exercise01-Claims/README.md) | Build a pipeline to ingest, transform, and load FHIR Claims data into a Dedicated SQL Pool. |
| [Exercise 02 - Observations](Exercise02-Observations/README.md) | Process FHIR Observations data and analyze time-series data with Azure Data Explorer. |
| [Exercise 03 - Patients](Exercise03-Patients/README.md) | Load FHIR Patient data using a Data Flow Activity and serve it through a Dedicated SQL Pool. |

## Configuration Parameters

Each pipeline exercise requires you to supply the following parameters (set during deployment):

| Parameter | Description | Example |
|-----------|-------------|---------|
| `StorageName` | Name of your Synapse workspace ADLS account | `mystorage` |
| `DatabaseName` | Name of your database in Synapse Dedicated SQL Pool | `mydb` |
| `ServerName` | Name of your Synapse Dedicated SQL Pool | `myserver` |
| `SparkPoolName` | Name of your Synapse Spark Pool | `mysparkpool` |
| `DatasetSize` | Size of the dataset to copy to your data lake | `1tb` or `30tb` |

## Troubleshooting

If you encounter any issues during deployment or the exercises, see the [Troubleshooting guide](Troubleshooting/Readme.md).

## Contributing

We welcome contributions! To contribute:

1. Fork the repository and create a feature branch.
2. Make your changes, ensuring screenshots and instructions match the current Azure portal experience.
3. Submit a pull request with a clear description of your changes.

To report bugs or request enhancements, please [open an issue](https://github.com/chikamsoachumsft/AzureSynapseEndToEndDemo/issues).

## License

This project is licensed under the [MIT License](LICENSE).
