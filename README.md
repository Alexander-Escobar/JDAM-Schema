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
  <b>JSON Declarative Application Model (JDAM)</b><br>Especificación para definir aplicaciones completas utilizando un único documento JSON declarativo.
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

## Descripción general
JDAM (JSON Declarative Application Model) es una especificación abierta que permite describir aplicaciones completas mediante un único documento JSON declarativo.

En lugar de implementar manualmente esquemas de bases de datos, API, formularios, validaciones, reglas de seguridad y flujos de trabajo, JDAM permite definir estos componentes como metadatos y generarlos automáticamente mediante herramientas compatibles.

La especificación sirve como fuente única de información para todo el ciclo de vida de la aplicación.

### 📦 ¿Por que, JDAM?

¿Qué es JDAM?

JDAM (JSON Declarative Application Model) es un modelo declarativo basado en JSON que permite definir aplicaciones completas utilizando un único documento estructurado.

Las aplicaciones modernas suelen requerir un desarrollo repetitivo en múltiples capas:

* Esquemas de bases de datos
* API REST
* Reglas de validación
* Interfaces de usuario
* Autenticación
* Flujos de trabajo empresariales
* Lógica de integración

JDAM elimina esta duplicación centralizando las definiciones de la aplicación en un único modelo.

```text
Modelo JDAM
     ┿
     ├── Estructura de la base de datos
     ├── Definición de la API
     ├── Reglas de seguridad
     ├── Metadatos de la interfaz de usuario
     ├── Reglas de validación
     └── Pipelines de negocio
```


### Filosofía

JDAM sigue el principio:

"Describe la aplicación, no la implementación."

El desarrollador define el modelo y las herramientas compatibles generan automáticamente:

* Base de datos
* API REST
* Formularios
* Catálogos
* Validaciones
* Integraciones
* Automatizaciones

### Objetivos
* Reducir código repetitivo
* Mantener una única fuente de verdad
* Permitir generación automática

Evitar escribir manualmente:

* Modelos ORM (Mapeo Objeto-Relacional)
* DTOs (Data Transfer Object o Objeto de Transferencia de Datos)
* Validadores
* CRUDs (Create, Read, Update, Delete)
* Endpoints
* Formularios


Todo el sistema se describe desde un único archivo JDAM.

JDAM

 ├─ Database  
 
 ├─ API  
 
 ├─ UI  
 
 ├─ Security  
 
 └─ Business Rules  
 


JDAM está diseñado para ser consumido por motores como:

* MinervaJS / Owlet
* Generadores Frontend
* Generadores Backend
* Generadores SQL


## Principios fundamentales

### Enfoque declarativo

Describe qué es la aplicación, no cómo se implementa.

### Fuente única de verdad

Todas las capas de la aplicación se derivan del mismo modelo.

### Independencia de la base de datos

Las aplicaciones pueden dirigirse a múltiples motores de bases de datos mediante asignaciones de proveedores.

### Independencia de la API

La especificación describe los recursos y comportamientos independientemente de los marcos de implementación.

### Impulsado por la interfaz de usuario

Las interfaces de usuario se pueden generar directamente a partir de los metadatos del modelo.

### Extensible

Los metadatos personalizados y las extensiones específicas de la plataforma pueden coexistir sin afectar a la portabilidad.

---

## Características

### Definición de la aplicación

Define los metadatos a nivel de aplicación y la configuración de seguridad.

### Modelado de bases de datos

Describa tablas, columnas, relaciones y restricciones.

### Generación de API REST

Configure puntos finales CRUD directamente desde el modelo.

### Metadatos de la interfaz de usuario

Genere formularios, controles, validaciones y experiencias de usuario.

### Seguridad

Compatibilidad con:

* JWT
* Claves de API
* Autenticación básica
* OAuth2

### Pipelines de negocio

Ejecute lógica personalizada antes y después de las operaciones.

### Asignación de proveedores

Capa de abstracción de bases de datos compatible con:

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

## Ámbitos de aplicación

JDAM es especialmente adecuado para:

* Sistemas ERP
* Plataformas CRM
* Sistemas de inventario
* Aplicaciones administrativas
* Soluciones de back-office
* Herramientas empresariales internas
* Aplicaciones basadas en metadatos
* Plataformas low-code
* Generadores CRUD
* Sistemas empresariales

---

## Documentación

| Documento           | Descripción                                   |
| ------------------- | --------------------------                    |
| introduction.md     | Introducción a JDAM                           |
| philosophy.md       | Filosofía de diseño                           |
| getting-started.md  | Guía de inicio rápido                         |
| schema-reference.md | Referencia completa de esquemas               |
| application.md      | Configuración de la aplicación                |
| security.md         | Modelo de seguridad                           |
| dbprovider.md       | Asignaciones de proveedores de bases de datos |
| models.md           | Modelos y entidades                           |
| tables.md           | Definiciones de tablas                        |
| columns.md          | Definiciones de columnas                      |
| constraints.md      | Restricciones de la base de datos             |
| api.md              | Configuración de la API REST                  |
| pipelines.md        | Pipelines de negocio                          |
| ui-controls.md      | Controles de la interfaz de usuario           |
| migration-guide.md  | Guía de migración de versiones                |

---

## Ecosistema

JDAM está diseñado para ser utilizado por generadores, entornos de ejecución y herramientas de desarrollo capaces de transformar modelos declarativos en aplicaciones ejecutables.

Algunos ejemplos son:

* Generadores de backend
* Generadores de frontend
* Generadores de SQL
* Generadores de documentación
* Entornos de ejecución de aplicaciones
* Motores de transformación de modelos

---

## Control de versiones

JDAM sigue el sistema de control de versiones semántico.

```text
MAJOR.MINOR.PATCH

1.4.0
┿┿└── Patch
┿└──── Minor
└────── Major
```

---

## Colaboración

Se agradecen las contribuciones, los debates y las propuestas de mejora.

Por favor, abre una incidencia o envía una solicitud de extracción describiendo la mejora propuesta.


---


## License

BSD-2-Clause License

Copyright (c) JDAM Contributors

---

## Keywords

JSON Schema, Declarative Applications, Low-Code, Metadata Driven Development, Model Driven Architecture, REST API Generation, CRUD Generator, Database Modeling, Enterprise Applications, JDAM, JSON Declarative Application Model.

