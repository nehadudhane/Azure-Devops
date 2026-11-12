# Azure Data Factory — Data Engineering & Orchestration Project

## Overview

This repository contains Azure Resource Manager (ARM) exports for an Azure Data Factory (ADF) project, including pipelines, datasets, linked services, an integration runtime, and mapping data flows. It documents data ingestion, transformation, and serving configurations as defined in the exported templates.

## Technology and resources

- **Azure Data Factory** — workflow orchestration and pipeline definitions
- **ADF Mapping Data Flows** — transformation and serving definitions
- **Azure SQL / storage / HTTP / GitHub sources** — connections represented by linked services and datasets
- **ARM templates** — exported deployment configuration

## Components in the exports

The complete `ARMTemplateForFactory.json` defines:

| Resource type | Count |
| --- | ---: |
| Pipelines | 7 |
| Mapping data flows | 2 |
| Datasets | 13 |
| Linked services | 6 |
| Integration runtime | 1 |

**Pipelines:** `API_ingestion`, `GoldLayer`, `Parentpipeline`, `SQLtoDatalake`, `new_pipeline`, `onprem_ingestion`, and `silverpipeline`.

**Data flows:** `DataTransformation` and `dataserving`.

These names are taken from the exported artifacts. They do not by themselves establish end-to-end execution results or data volumes.

## Repository structure

```text
azuredevops/
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

The root ARM template is a full export. The linked templates represent an alternative split deployment structure; they overlap with the root export and should not be interpreted as additional independent pipelines.

## Security and portability

These are **environment-specific exports**. Before making this repository public, review linked-service endpoints, workspace/resource identifiers, account and server names, and any credential parameters or stored values. Supply secrets securely when deploying to another environment. The files are based on the original exports. For safe public sharing, the signed HTTP-trigger URL signature in two ARM JSON files has been replaced with `REDACTED_FOR_PUBLIC_REPOSITORY`. All other original configuration content is preserved. These templates are for documentation and will require valid credentials and environment settings for deployment.

## Author

**Neha Dudhane** — [GitHub](https://github.com/nehadudhane)
