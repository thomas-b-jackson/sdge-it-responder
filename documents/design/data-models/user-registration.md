```mermaid
---
title: Responder User Registration
---
erDiagram
  SECTION    ||--|| POSITION : includes

  SECTION {
    String name           "dynamo"
    postion[] positions   "dynamo"
  }

  POSITION {
    String name  "dynamo"
  }

  USER {
    String name  "dynamo"
    String email "dynamo"
    String role  "dynamo"
    Position position  "dynamo"
  }

```
