# Overview

Role-based access to applications, pages, and api calls in the responder app.

# Infrastruction Authorization

The first level of end-user authorization is enforced by a security group that is configured with the responder EntraID application, as described in TBD.

Thus, users must have Sempra credentials AND be a member of the security group to access the responder app.

Additional authorization controls are provided by roles defined WITHIN the responder application.

# User Roles

Access to each web and api resources is controlled via user role.

Supported roles are per the `Role` enum in [api/schemas/user-registration.graphql](../../api/schemas/user-registration.graphql).

Users are provisioned either manaully, or via the registration process.

# API Authorization Controls

Every api query and mutation defined in the api schema includes an `@auth` directive. The directive takes as an argument an array of roles. A user's role must be included in the roles in the directive array in order to make calls to the associated query or mution.

# Web Authorization Controls

The first level of web-based authorization controls are defined against each page or resource.

> Note: The details are TBD for now.
