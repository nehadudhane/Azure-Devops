# Azure Data Factory — Data Engineering & Orchestration Project

## Overview

Azure Resource Manager (ARM) exports documenting an **Azure Data Factory (ADF)** project, including data ingestion, orchestration, mapping data flows, datasets, linked services, and an integration runtime.

## Technology Stack

- Azure Data Factory
- ADF Mapping Data Flows
- Azure SQL, storage, HTTP and GitHub connections represented in the exported configurations
- Azure Resource Manager (ARM) JSON templates

## Components in the Export

The complete `ARMTemplateForFactory.json` defines:

| Resource type | Count |
| --- | ---: |
| Pipelines | 7 |
| Mapping data flows | 2 |
| Datasets | 13 |
| Linked services | 6 |
| Integration runtime | 1 |

**Pipelines:** `API_ingestion`, `GoldLayer`, `Parentpipeline`, `SQLtoDatalake`, `new_pipeline`, `onprem_ingestion`, and `silverpipeline`.

**Mapping data flows:** `DataTransformation` and `dataserving`.

The listed names and counts describe configured resources; they are not a claim about execution results or volume processed.

## Architecture at a Glance

```text
Source systems / API / Azure SQL / storage
                    |
                    v
          Azure Data Factory
      Pipelines and linked services
                    |
                    v
          Mapping data flows
      DataTransformation / dataserving
                    |
                    v
         Configured data sinks
```

The detailed sources and destinations are defined in the ARM exports.

## Repository Structure

```text
Azure-Devops/
├── README.md
├── ARMTemplateForFactory.json
├── ARMTemplateParametersForFactory.json
├── factory/
│   ├── AzureDevopsneha_ARMTemplateForFactory.json
│   └── AzureDevopsneha_ARMTemplateParametersForFactory.json
└── linkedTemplates/
    ├── ArmTemplate_0.json
    ├── ArmTemplate_1.json
    ├── ArmTemplate_master.json
    └── ArmTemplateParameters_master.json
```

The root ARM template and the linked templates are alternative exports of overlapping resources; they do not represent independent sets of pipelines.

## Security and Deployment Notes

These are environment-specific ARM exports. The **public-sharing versions** of two templates replace an exposed signed HTTP-trigger URL signature with `REDACTED_FOR_PUBLIC_REPOSITORY`. All other configuration content in those files is preserved.

The exports may include environment identifiers and endpoint names. Do not publish live credentials, and configure all required secrets and environment values securely before deployment. Redacted templates are for portfolio documentation, not direct deployment as-is.

## Author

**Neha Dudhane** — [GitHub](https://github.com/nehadudhane)
