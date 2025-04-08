Notes:

1. credentials need to be audited separately from trainings
1. evaluations apply to command and general staff only
1. credentials are to evaluations what certificates are to trainings
1. operational periods are the columns in the roster

```mermaid
---
title: Responder MVP
---
erDiagram
  INCIDENT ||--|| ROSTER : staffing-response-to
  ROSTER     ||--|| SECTION : includes
  SECTION    ||--|| POSITION : includes
  POSITION   ||--|| INCIDENT-DAY : includes
  INCIDENT-DAY  ||--|| RESPONDER : staffed-by
  INCIDENT-DAY  ||--|| LEADER : supported-by
  RESPONDER  ||--|| TRAINING : takes
  RESPONDER  ||--|| CERTIFICATE : obtains
  RESPONDER  ||--|| EVALUATION : receives
  RESPONDER  ||--|| RECOGNITION-PAY : earns

  APPROVAL {
    ID id
    Postion position
    Responder responder
  }

  APPROVAL-RESPONSE {
    ID id
    ID appproval-id
    string approver
    string comment
  }

  ROSTER {
    ID id
    OperationalPeriod[] operationPeriods
  }

  OPERATIONAL-PERIOD {
    Responder[] responders
  }

  SECTION {
    ID id
    postion[] positions
  }

  POSITION {
    ID id
    IncidentDay[] days
  }

  INCIDENT-DAY {
    ID id
    Reponder[] responders
  }

  COMMAND-AND-GENERAL-STAFF {
    ID id
    ID supported-by
    string name
    LeaderRole role
    Evaluation[] evaluations
  }

  RESPONDER {
    ID id
    ID supported-by
    string name
    Postion position
    datetime started
    ResponderStatus status
  }

  INCIDENT {
    ID id
    datetime start "TBD"
    datetime end  "TBD"
    ActivationType type
  }

  INCIDENT {
    ID id
    ID incident-id
  }

  COURSE {
    ID id
    string name
    CourseType type "Onboarding|Position|Foo"
    Document[] documents
  }

  TRAINING {
    ID id
    Course course
    datetime completed
    Responder responder
    Certificate certificate
  }

  CERTIFICATE {
    ID id
    ID training-id
  }

  CERTIFICATE-APPROVAL {
    ID id
    ID cert-id
    boolean approved
    string rejectionComment
    name approver
  }

  RECOGNITION-PAY {
    ID id
  }

  CREDENTIAL {
    ID id
    ID evaluation-id
  }

  EVALUATION {
    ID id
    ID incident-id
    ID responder-id
    Performance performanceReview
  }

```
