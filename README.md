# Knowledge-Driven Business Request Automation

AI-powered workflow for business request classification, Text-to-SQL retrieval, and automated reporting.

<img width="1577" height="821" alt="image" src="https://github.com/user-attachments/assets/8422b067-245f-4886-b4bf-a2e8466bca43" />


## Overview

This project demonstrates how artificial intelligence can automate the processing of business requests received through email by combining workflow automation, knowledge-based classification, structured information extraction, PostgreSQL queries, and automated report generation.

The objective is not simply to automate email processing, but to transform unstructured organizational requests into executable business workflows driven by business rules and information models.

The architecture combines AI-assisted classification, parameter extraction, SQL generation, and automated reporting within a single workflow orchestration process.

## The Business Problem

Organizations frequently receive operational requests through email.

Typical requests require:

* understanding the business context;
* identifying the request category;
* extracting relevant parameters;
* retrieving information from enterprise databases;
* generating reports;
* responding consistently to users.

Manual processing is time-consuming and difficult to standardize.

## The Solution

The workflow automatically performs the following process:

1. Receives incoming emails.
2. Cleans and extracts the relevant request content.
3. Classifies the request using a Large Language Model.
4. Extracts structured business parameters.
5. Maps the request to a predefined business catalog.
6. Generates parameterized SQL queries.
7. Retrieves information from PostgreSQL.
8. Generates an Excel report.
9. Sends an automated response.

## Workflow Architecture

Incoming Email
│
▼
Content Extraction
│
▼
AI Classification
│
▼
Business Catalog
│
▼
Text-to-SQL Generation
│
▼
PostgreSQL Query
│
▼
Excel Report Generation
│
▼
Automated Email Response

## Key Features

### Business Process Automation

Automates the complete lifecycle of structured business requests.

### AI-Based Classification

Uses natural language understanding to identify request categories and extract relevant business parameters.

### Text-to-SQL

Converts natural language requests into parameterized SQL queries using a controlled business catalog.

### Knowledge-Driven Design

Separates business knowledge from implementation logic through a catalog-based architecture.

### Automated Reporting

Generates structured Excel reports and standardized responses automatically.

## Technologies

* n8n
* PostgreSQL
* SQL
* Groq LLM
* AI Information Extraction
* Workflow Automation
* Text-to-SQL
* Business Process Modeling

## Design Principles

This project follows several architectural principles:

* explicit business rules;
* structured knowledge representation;
* controlled AI decision boundaries;
* parameterized SQL generation;
* workflow transparency;
* separation between knowledge and execution.

## Repository Structure

* **architecture/**: system and workflow diagrams
* **n8n/**: sanitized workflow definition
* **docs/**: architecture and business design documentation
* **sql/**: sample business catalog structure
* **screenshots/**: workflow illustrations

## Why This Project Matters

The most valuable aspect of this project is not the workflow itself.

It is the modeling approach.

The workflow demonstrates how organizational knowledge, business rules, and information structures can be transformed into systems that are easier to automate, maintain, and evolve.

------------------
Repository Notice

The workflow included in this repository is a sanitized reference implementation.

All organization-specific information has been removed, including:

database schemas,
table names,
SQL queries,
credentials,
email addresses,
workflow identifiers,
and institutional business processes.

The purpose of the repository is to demonstrate the architecture, business modeling approach, and AI-assisted workflow design, not to reproduce any production implementation.

This project represents a practical example of **AI-enabled business systems design**, where technology serves a clearly modeled business process rather than replacing business understanding.
