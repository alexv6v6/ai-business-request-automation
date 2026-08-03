# Workflow explanation

## From business requests to executable workflows

This project was designed around a simple question:

**How can an organization transform unstructured business requests into standardized, traceable, and automated processes?**

The solution was not built by starting with automation technology.

It was built by modeling the business process first.

## The core challenge

Business requests arrive in natural language through email.

A typical request contains:

* implicit business context,
* incomplete information,
* variable terminology,
* different writing styles,
* and multiple possible interpretations.

A purely rule-based workflow becomes increasingly difficult to maintain as the number of request types grows.

The key design decision was to separate **business knowledge** from **workflow execution**.

## Conceptual architecture

The workflow is organized into four logical layers.

### 1. Request interpretation

The incoming email is processed to extract the relevant business content while removing signatures, formatting, and unnecessary metadata.

The objective is to obtain a clean business request.

### 2. Knowledge classification

Instead of generating SQL directly from the email, the request is mapped to a **controlled business catalog**.

This catalog defines:

* request categories,
* business concepts,
* required parameters,
* expected outputs,
* and associated query templates.

This significantly reduces ambiguity and improves governance.

### 3. Structured parameter extraction

The AI model extracts only the parameters required by the business catalog.

Examples include:

* year,
* region,
* process type,
* report scope,
* and operational filters.

The AI does not decide the business logic.

It identifies structured values within predefined boundaries.

### 4. Query execution and reporting

The extracted parameters are used to generate parameterized SQL queries.

The workflow then:

* retrieves the data,
* generates a structured Excel report,
* prepares a standardized response,
* and delivers the requested information automatically.

## Why the catalog matters

The business catalog is the most important component of the architecture.

It acts as a **knowledge layer** between natural language and database queries.

Without the catalog, every new request type would require changes to the workflow.

With the catalog, the system becomes extensible.

New request types can be incorporated by expanding business knowledge rather than redesigning the automation.

## AI boundaries

A deliberate design decision was to limit the role of AI.

The model is responsible for:

* classification,
* entity extraction,
* and parameter identification.

The model is **not responsible for business calculations, regulatory interpretation, or unrestricted SQL generation**.

Business rules remain explicit and controlled.

This improves:

* consistency,
* auditability,
* maintainability,
* and institutional reliability.

## Business systems perspective

From a systems analysis perspective, this project demonstrates three important principles.

### Knowledge precedes automation

A poorly understood process cannot be automated effectively.

### Business rules must be explicit

Hidden institutional knowledge creates fragile systems.

### AI works best with structured knowledge

The highest value comes from combining AI capabilities with well-modeled business information.

## The design philosophy

This workflow is not primarily an email automation.

It is an example of **knowledge-driven business systems design**.

The automation layer executes the process.

The information model defines the process.

The business catalog governs the process.

And AI assists the process.

The architecture can be generalized to many organizational contexts, including regulatory workflows, operational requests, service management, reporting automation, and enterprise knowledge retrieval systems.
