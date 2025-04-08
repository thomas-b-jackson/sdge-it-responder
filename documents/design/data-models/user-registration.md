# Overview

An entity-relationship-diagram (ERD) representing the business objects used in responder user registration processes.

# ERD

![alt text](./user-registration.png)

# Appendix: Mermaid Sources

```mermaid
---
title: Responder User Registration
---
erDiagram
  Section  ||--|| Postition : includes
  User  ||--|| Postition : includes
  User  ||--|| Application : includes

  Section {
    name string
    positions Postion[]
  }

  Postition {
    name string
    section Section
  }

  User {
    name string
    email string
    role Role
    position Position
    since datetime
    application Application
  }

  Application {
    position Position
    status ApplicationStatus
    rejectionReason string
  }
```
