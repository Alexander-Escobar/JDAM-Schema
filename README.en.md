<p align="right">
  <a href="./README.md">
    <img src="https://img.shields.io/badge/🇪🇸-Español-red" alt="Español">
  </a>
  <a href="./README.en.md">
    <img src="https://img.shields.io/badge/🇺🇸-English-blue" alt="English">
  </a>
</p>

<h1 align="center">
  JDAM de MinervaJS
</h1>
<p align="center">
  <b>JSON Declarative Application Model (JDAM)</b><br>Specification for defining complete applications using a single declarative JSON document.
</p>

<p align="center">
	<img src="https://img.shields.io/badge/version-1.4.0-blue" alt="Version">
	<img src="https://img.shields.io/badge/JDAM-1.4.0-0066cc" alt="JDAM">
	<img src="https://img.shields.io/badge/status-stable-success" alt="Status">
	<img src="https://img.shields.io/badge/schema-JSON-orange" alt="Schema">
	<img src="https://img.shields.io/badge/specification-official-blueviolet" alt="Specification">
	<img src="https://img.shields.io/badge/Low--Code-yes-success" alt="Low Code">
	<img src="https://img.shields.io/badge/Model--Driven-Architecture-blue" alt="MDA">
	<img src="https://img.shields.io/badge/REST-Ready-red" alt="REST Ready">
	<img src="https://img.shields.io/badge/license-BSD--2--Clause-green" alt="License">
</p>

---

## Overview

JDAM (**JSON Declarative Application Model**) is an open specification that enables describe complete applications through a single declarative JSON document.

Instead of manually implementing database schemas, APIs, forms, validations, security rules, and business workflows, JDAM allows these components to be defined as metadata and generated automatically by compatible tools.

The specification serves as a single source of truth for the entire application lifecycle.

---

## Why JDAM?

Modern applications often require repetitive development across multiple layers:

* Database schemas
* REST APIs
* Validation rules
* User interfaces
* Authentication
* Business workflows
* Integration logic

JDAM eliminates this duplication by centralizing application definitions into a single model.

```text
JDAM Model
     �?
     ├── Database Structure
     ├── API Definition
     ├── Security Rules
     ├── UI Metadata
     ├── Validation Rules
     └── Business Pipelines
```

---

## Core Principles

### Declarative First

Describe what the application is, not how it is implemented.

### Single Source of Truth

All application layers are derived from the same model.

### Database Agnostic

Applications can target multiple database engines through provider mappings.

### API Agnostic

The specification describes resources and behaviors independently of implementation frameworks.

### UI Driven

User interfaces can be generated directly from model metadata.

### Extensible

Custom metadata and platform-specific extensions can coexist without affecting portability.

---

## Features

### Application Definition

Define application-level metadata and security configuration.

### Database Modeling

Describe tables, columns, relationships, and constraints.

### REST API Generation

Configure CRUD endpoints directly from the model.

### UI Metadata

Generate forms, controls, validations, and user experiences.

### Security

Support for:

* JWT
* API Keys
* Basic Authentication
* OAuth2

### Business Pipelines

Execute custom logic before and after operations.

### Provider Mapping

Database abstraction layer supporting:

* MariaDB
* MySQL
* PostgreSQL
* Oracle

---

## Quick Example

```json
{
  "application": {
    "name": "Inventory System"
  },

  "models": {
    "tables": [
      {
        "name": "product",
        "table": "products",
        "title": "Products",

        "columns": [
          {
            "col": "id",

            "db": {
              "type": "uuid",
              "required": true
            },

            "validation": {},

            "UI": {
              "label": "Identifier",
              "control": ["hidden", {}]
            }
          },

          {
            "col": "name",

            "db": {
              "type": "string",
              "length": 100,
              "required": true
            },

            "validation": {
              "minLength": 3
            },

            "UI": {
              "label": "Product Name",
              "control": ["text", {}]
            }
          }
        ]
      }
    ]
  }
}
```

---

## Supported Domains

JDAM is especially suitable for:

* ERP Systems
* CRM Platforms
* Inventory Systems
* Administrative Applications
* Backoffice Solutions
* Internal Business Tools
* Metadata Driven Applications
* Low-Code Platforms
* CRUD Generators
* Enterprise Systems

---

## Documentation

| Document            | Description                |
| ------------------- | -------------------------- |
| introduction.md     | Introduction to JDAM       |
| philosophy.md       | Design philosophy          |
| getting-started.md  | Quick start guide          |
| schema-reference.md | Complete schema reference  |
| application.md      | Application configuration  |
| security.md         | Security model             |
| dbprovider.md       | Database provider mappings |
| models.md           | Models and entities        |
| tables.md           | Table definitions          |
| columns.md          | Column definitions         |
| constraints.md      | Database constraints       |
| api.md              | REST API configuration     |
| pipelines.md        | Business pipelines         |
| ui-controls.md      | UI controls                |
| migration-guide.md  | Version migration guide    |

---

## Ecosystem

JDAM is designed to be consumed by generators, runtimes, and development tools capable of transforming declarative models into executable applications.

Examples include:

* Backend generators
* Frontend generators
* SQL generators
* Documentation generators
* Application runtimes
* Model transformation engines

---

## Versioning

JDAM follows semantic versioning.

```text
MAJOR.MINOR.PATCH

1.4.0
�?�?└── Patch
�?└──── Minor
└────── Major
```

---

## Contributing

Contributions, discussions, and improvement proposals are welcome.

Please open an issue or submit a pull request describing the proposed enhancement.

---

## License

BSD-2-Clause License

Copyright (c) JDAM Contributors

---

## Keywords

JSON Schema, Declarative Applications, Low-Code, Metadata Driven Development, Model Driven Architecture, REST API Generation, CRUD Generator, Database Modeling, Enterprise Applications, JDAM, JSON Declarative Application Model.


