# Overview

This project was part of a large-scale data modernization initiative at Accenture, where we were tasked with **replacing Oracle GoldenGate**, a costly and legacy middleware component, without disrupting data flows to over **50 critical downstream applications**. The project demanded high reliability, zero downtime, and complete data consistency to meet stringent SLAs for real-time enterprise operations.

# Problem Statement

Oracle Fusion Applications served as the primary data source for several downstream enterprise systems. However, the data movement layer relied on Oracle GoldenGate, which incurred significant licensing costs and lacked flexibility for change.

**Key challenges included:**

- Eliminating Oracle GoldenGate without interrupting downstream data pipelines  
- Rebuilding 1:1 data flows to over 50 systems, ensuring the **exact same format** and **same time window**  
- Preserving **zero-downtime** availability during migration due to the critical nature of the consuming systems (even a one-hour delay was unacceptable)  

# Objective

The team’s mission was to **fully decommission Oracle GoldenGate** and **implement a new, robust ETL architecture** that:

- Maintains all existing data delivery SLAs  
- Supports transformation and routing logic with better observability  
- Reduces cost and production incidents

# Architecture & Solution Design

To achieve this, we developed a **layered architecture** with the following flow:

Oracle Fusion Source → Staging Layer → ODS Layer (via Informatica) → Downstream Systems (via PL/SQL and Autosys)


# Key Components

| Component              | Description                                                                 |
|------------------------|-----------------------------------------------------------------------------|
| **Staging Layer**      | Initial raw data dump from Oracle Fusion                                   |
| **Informatica Mappings** | Performed transformations and loading into ODS                           |
| **PL/SQL Procedures**  | Maintained output formats for each downstream system                        |
| **AutoSys Batch Jobs** | Scheduled and orchestrated all data flows end-to-end                        |
| **CI/CD with Git**     | Standardized development, version control, and deployment pipelines         |

# Tools & Technologies Used

| Tool / Tech             | Purpose                                              |
|-------------------------|------------------------------------------------------|
| Oracle Fusion           | Primary data source                                  |
| Informatica PowerCenter | ETL development for 250+ workflows                   |
| PL/SQL                  | Format-preserving procedures for target systems      |
| AutoSys                 | Orchestration of 350+ ETL batch jobs                 |
| Git                     | Source control and CI/CD automation                  |
| Shell Scripts           | Integration and system-level tasks                   |

# Result

This project delivered measurable impact across cost, reliability, and performance:

- **$70,000/year saved** by eliminating Oracle GoldenGate licensing  
- **20% improvement in data availability**, reducing lag for business-critical systems  
- **Lowered production incidents** due to simplified architecture and robust ETL controls  

# Learnings & Takeaways

- Achieving seamless migration in a high-stakes, zero-downtime environment requires meticulous planning, parallel testing, and gradual rollout strategies.  
- Investing in clean, modular ETL design (250+ mappings) pays off in maintenance and debugging.  
- Orchestration (AutoSys) is just as critical as transformation—ensuring timeliness and recovery.  
