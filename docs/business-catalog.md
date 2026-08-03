# Business catalog architecture

## The knowledge layer behind the workflow

The business catalog is the central architectural component of this project.

It serves as the **knowledge layer** that connects natural language requests with controlled business operations.

Instead of allowing the workflow to interpret every request independently, the catalog provides a structured representation of organizational knowledge, business concepts, and approved information retrieval logic.

The workflow executes the process.

The catalog defines the meaning of the process.

## Why a business catalog?

Enterprise requests are often expressed using inconsistent language.

Different users may refer to the same business concept using different terminology.

For example:

* operational report,
* historical information,
* annual statistics,
* process summary,
* regional analysis.

Although these expressions vary, they frequently correspond to the same underlying business operation.

The catalog normalizes this variability into a controlled business model.

## Conceptual role

The catalog performs three essential functions.

### Semantic normalization

Maps natural language expressions to standardized business categories.

### Business rule governance

Defines the approved business meaning of each request type.

### Query orchestration

Associates each business category with validated data retrieval logic.

This separation allows AI to interpret language while the organization retains control over business behavior.

Catalog structure

Each catalog entry represents a business capability and acts as a formal definition of how a specific type of request should be interpreted and executed.

A catalog entry contains five essential components.

Request type

Defines the standardized business category used by the system. This allows different natural language expressions to be normalized into a single operational concept.

Business definition

Describes the organizational meaning of the request and clarifies the business context that the category represents.

Required parameters

Specifies the structured information needed for execution, such as year, region, process type, or other business attributes extracted from the request.

SQL template

Contains the approved parameterized query associated with the business category. The SQL implementation is controlled by the catalog rather than generated freely by the AI model.

Output definition

Defines the expected result of the request, including report format, analytical scope, and delivery method.

Example catalog entry

The following example illustrates how a request is represented inside the catalog.

Request Type
Annual operational report

Business Category
Operational analytics

Required Parameters
Year
Region

SQL Template
Parameterized query

Expected Output
Excel report

In this architecture, the AI model identifies the request category and extracts the required parameters, while the business catalog determines the approved execution logic and reporting behavior.

## Relationship with AI

A critical design decision was to ensure that **AI does not define business logic**.

The language model performs:

* request classification,
* entity recognition,
* parameter extraction,
* terminology normalization.

The catalog performs:

* business interpretation,
* rule definition,
* query selection,
* validation,
* and execution control.

This architecture provides both flexibility and governance.

## Controlled extensibility

One of the main advantages of the catalog-driven approach is that the system can evolve without significant workflow redesign.

Adding a new business capability typically requires:

1. defining the business category,
2. documenting the business meaning,
3. specifying the required parameters,
4. creating the SQL template,
5. and registering the validation rules.

The workflow architecture remains stable.

## From information architecture to automation

The catalog represents a formal information model.

It captures:

* business concepts,
* operational definitions,
* reporting structures,
* analytical dimensions,
* and information retrieval rules.

In this sense, the catalog functions as an **organizational knowledge base** rather than a configuration table.

## Architectural significance

From a business systems perspective, the catalog is the component that transforms the workflow from an automation script into an enterprise information system.

Natural language interfaces become reliable only when they are grounded in explicit business semantics.

The catalog provides that semantic foundation.

## The broader principle

Organizations do not automate emails.

They automate business capabilities.

Those capabilities are defined by business knowledge.

The business catalog is the mechanism that makes that knowledge explicit, governable, and executable.
