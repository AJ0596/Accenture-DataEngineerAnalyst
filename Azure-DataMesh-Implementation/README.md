# Overview

This project was a cloud modernization initiative at Accenture for a large financial/banking client. The legacy HR Data Integration Service had been running on on-prem systems for over 15 years. As part of the company’s broader digital transformation, our team was tasked with **rearchitecting this service on Microsoft Azure**—improving scalability, reliability, and reducing infrastructure cost.

I led the development effort, helping the team upskill in Azure services, build modular data pipelines, and enable near real-time access to HR data across 50+ downstream applications.

# Problem Statement

The existing system relied heavily on expensive legacy tools like Oracle and Informatica. Key business pain points included:

- High operational cost due to legacy software and on-prem maintenance  
- Inflexible architecture with long onboarding cycles for new data sources  
- Delivery latency of ~4 hours, making real-time insights impossible  
- Low trust in data due to limited observability and manual reconciliation  

# Objective

Our goal was to **migrate the HR Data Integration Service to Microsoft Azure** and deliver a fully cloud-native solution that:

- Decreases data delivery latency  
- Improves data quality through reconciliation mechanisms  
- Enables modular and reusable pipelines  
- Supports self-service and decentralized access to data  
- Cuts operational costs by decommissioning legacy tools  

# Architecture & Solution Design

We implemented a **Medallion Architecture** (Bronze → Silver → Gold) with decoupled layers and dynamic orchestration. Here's an abstract view of the flow:

Source Systems → Azure Databricks → Azure Data Factory → Azure Data Lake Gen2 → Azure SQL → Downstream Apps


# Key Components

| Component                   | Description                                                                 |
|-----------------------------|-----------------------------------------------------------------------------|
| **Azure Data Factory (ADF)**| Built 30+ reusable, parameterized pipelines for ingestion and transformation |
| **Azure Data Lake Gen2**    | Storage layer for raw, processed, and curated HR data                        |
| **Azure Databricks**        | Performed data cleaning using PySpark                                   |
| **Azure SQL Database**      | Hosted procedures for logging and reconciliation                             |
| **Azure Functions**         | Enabled custom logic, alerting, and orchestration between pipeline stages   |
| **Azure DevOps**            | Automated CI/CD deployment pipelines across environments                     |

# Tools & Technologies Used

| Tool / Tech          | Purpose                                                        |
|----------------------|----------------------------------------------------------------|
| Azure Data Factory   | Orchestration and transformation using parameterized pipelines |
| Azure Databricks     | Data cleaning with PySpark                    |
| Azure Data Lake Gen2 | Storage for Medallion architecture                             |
| Azure SQL            | Custom logging, validation, and reconciliation procedures      |
| Azure DevOps         | CI/CD pipelines, version control, release automation           |
| Agile / Jira         | Sprint planning, backlog grooming, and iterative delivery      |

# Result

The project delivered meaningful technical and business impact:

- **Data delivery time reduced from 4 hours to 30 minutes**, enabling near real-time insights  
- **$60K/year saved** in operational costs by replacing Informatica and Oracle licenses  
- **25% improvement in data reliability** due to built-in reconciliation and logging  
- **60% faster onboarding** of new data sources using reusable pipeline templates  
- **Accelerated release cycles by 40%** through Azure DevOps-based CI/CD automation  

# Learnings & Takeaways

- Upskilling across cloud services (ADF, MSSQL, DataBricks, DevOps) was crucial to long-term team success  
- A modular, parameterized design in ADF helps scale pipelines rapidly across sources  
- Reconciliation logic should be baked into the ETL—not added as an afterthought  
- Data Mesh principles helped break silos and empower downstream teams with self-serve access  

# Contact

Feel free to reach out at:
  Email: sneela7@uic.edu/saiajayneel@gmail.com
  Ph: +1 312 792 5326

