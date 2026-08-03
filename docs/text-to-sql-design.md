# Text-to-SQL architecture

## Controlled natural language to database access

Text-to-SQL systems are often presented as a simple problem:

**Natural language → SQL query**

In practice, enterprise environments require a much more controlled architecture.

Business users rarely know the underlying database structure, but unrestricted SQL generation introduces significant risks related to security, consistency, governance, and business interpretation.

This project was designed around a different principle.

**The AI model interprets business language, but business knowledge controls database access.**

## The architecture

The system does not generate SQL directly from the user request.

Instead, it follows a structured decision process.

User request

↓

AI classification

↓

Business catalog

↓

Parameterized SQL template

↓

Database execution

↓

Structured response

The business catalog acts as an intermediate semantic layer between natural language and the database.

## Why not generate SQL freely?

Allowing a language model to generate arbitrary SQL creates several problems.

### Ambiguous business interpretation

The same request may correspond to multiple business concepts.

### Inconsistent calculations

Different SQL queries may implement the same business rule differently.

### Regulatory risk

Enterprise data often requires controlled access patterns.

### Maintenance complexity

Prompt engineering alone becomes difficult to maintain as business logic evolves.

The catalog-driven architecture addresses these issues.

## The business catalog

Each catalog entry contains:

* business category;
* business definition;
* required parameters;
* SQL template;
* reporting purpose;
* and output structure.

The AI model selects the business category.

The catalog determines the SQL implementation.

## Parameter extraction

The language model extracts only the values required by the selected business category.

Typical parameters include:

* year;
* region;
* process type;
* operational status;
* reporting scope.

The extracted values are validated before query execution.

## Parameterized SQL

Instead of constructing SQL dynamically through prompt generation, the system uses predefined parameterized queries.

Conceptually:

SELECT ...

FROM ...

WHERE process_type = :type

AND year = :year

AND region = :region

This provides:

* consistent business logic;
* protection against malformed queries;
* predictable performance;
* easier validation;
* and simpler governance.

## Separation of responsibilities

A critical design principle is the separation between AI and business logic.

AI responsibilities:

* classify requests;
* identify entities;
* extract parameters;
* normalize terminology.

Business system responsibilities:

* define business categories;
* implement business rules;
* execute SQL;
* validate results;
* generate reports.

This separation significantly improves reliability.

## Explainability

Because the SQL originates from the business catalog, every query can be traced back to:

* a business category;
* a documented business definition;
* and an approved query template.

This creates an auditable decision chain.

Natural language

↓

Business category

↓

SQL template

↓

Query execution

↓

Report

The resulting process is explainable and reproducible.

## Extensibility

New business capabilities can be added by extending the catalog rather than redesigning the AI workflow.

A new analytical request requires:

* a business definition;
* a parameter specification;
* and a SQL template.

The workflow architecture remains unchanged.

## Relationship with business systems analysis

From a business systems perspective, the most important component is not the language model.

It is the **semantic model** represented by the business catalog.

The catalog defines how organizational concepts map to structured information.

The AI model becomes a translation layer rather than a decision authority.

## The broader design principle

Text-to-SQL should not be treated primarily as an AI problem.

It should be treated as a **business modeling problem**.

When business concepts, rules, and information structures are modeled explicitly, AI can provide a natural language interface without compromising consistency, governance, or maintainability.

The value of the architecture comes from the quality of the business model, not from unrestricted query generation.
