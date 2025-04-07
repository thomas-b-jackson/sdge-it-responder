```mermaid
---
title: Responder User Registration
---
erDiagram
  Section  ||--|| Postition : includes

  Section {
    String name           "dynamo"
    Postion[] positions   "dynamo"
  }

  Postition {
    String name  "dynamo"
  }

  User {
    String name  "dynamo"
    String email "dynamo"
    UserRole role  "dynamo"
    Position position  "dynamo"
  }

```
