# AI Business Request Automation

AI-powered workflow for business request classification, Text-to-SQL retrieval, and automated reporting.

## Overview

Organizations often receive a large volume of operational and business requests through email. Processing these requests manually requires reading the message, identifying the request type, retrieving information from enterprise databases, generating reports, and responding to the requester.

This project demonstrates an AI-powered automation workflow that transforms unstructured email requests into structured business actions.

The system combines workflow automation, natural language understanding, SQL generation, and automated reporting to reduce manual processing time while improving consistency and traceability.

## The Problem

Business requests typically arrive in natural language.

Examples include:

* requests for operational reports;
* requests filtered by year or region;
* requests for business process information;
* requests requiring structured data extraction.

Traditionally, these requests require manual interpretation and database querying.

## The Solution

The workflow automatically:

1. Receives incoming emails.
2. Extracts the relevant request content.
3. Identifies the business request category using AI.
4. Extracts structured parameters (such as year and region).
5. Maps the request to a predefined business catalog.
6. Generates parameterized SQL queries.
7. Retrieves data from PostgreSQL.
8. Generates an Excel report.
9. Sends an automated response with the requested information.

## System Architecture

Email → AI Classification → Business Catalog → SQL Generation → PostgreSQL → Excel Report → Email Response

## Key Capabilities

* AI-powered request classification
* Text-to-SQL
* Business rules automation
* PostgreSQL integration
* Workflow orchestration with n8n
* Automated Excel reporting
* Email response automation
* Knowledge-based business catalog

## Technologies

* n8n
* PostgreSQL
* SQL
* Groq LLM
* AI Information Extraction
* Text-to-SQL
* Workflow Automation

## Architecture

See the `architecture/` folder for the complete workflow and system diagrams.

## Documentation

* `docs/business-rules.md`
* `docs/text-to-sql-design.md`
* `docs/workflow-explanation.md`

## Design Philosophy

This project is not primarily about AI.

It is about transforming organizational knowledge into executable systems.

The workflow demonstrates how business rules, process knowledge, and structured information can be modeled in a way that allows AI systems to automate operational tasks while preserving business consistency and governance.
