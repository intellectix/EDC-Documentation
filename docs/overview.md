---
id: overview
title: Enterprise Data Coordinator Overview
sidebar_label: EDC Overview
---

The EDC revolutionizes the way application developers work with data. Rather than having to setup data access, data permissioning and system logging for each new application, the EDC installs industry standard best practices directly into a pre-existing workflow to enable developers to build applications at a fraction of the time it would have originally taken.

Here are the main features of the EDC:

## Free Version

### EDC Dashboard

The EDC dashboard provides developers with a graphical interface to view their application's performance at a high level. It also allows developers to add database connections as well as see a history of all data requests being made by their application.

### Connectors

Connectors provide the core functionality of the EDC system. Rather than making connections to databases through code, developers can quickly add database connectors in the GUI. These connectors allow for all data requests to be routed through the EDC which gives developers a complete log history as requests are made.

By interacting with databases in this way, developers can focus on the front-end and business logic of their applications rather than taking the time to setup complicated back-end logic. Data requests can be made directly in controller methods without the need for pre-existing models or repositories.

### Request History

Request History provides full logging information about each request being made through the EDC in a single location. All requests are able to be selected to view the complete logging information to help developers pinpoint connection issues.

## Pro Version

In addition to the features available for Free users, the Pro Version of the EDC provides the following additional benefits:

### Roles

Roles allow for column-level database permissioning. By creating a Role, a developer is able to assign Users to that Role which determines how Users are able to interact with the data. For example, if there is a User table which contains SSN information, and the Role does not provide access to the SSN column, then the User will never be access the information. Permissions are applied before database requests are made, which guarantees a 0% chance of data leakage.

### App Keys

### Users

Users interact with the EDC based on the Role they have been assigned to. By default, a User has no access to any data until they have been assigned Role permissions. In addition, by requiring Users to be logged in to make data requests, the EDC is able to provide more in-depth logging information which allows developers to quickly see who is making database requests.

### Developer Console

The Pro Version of the EDC provides an additional GUI where developers can test database calls, see database Schemas and more. This console makes it easy to quickly test database calls without having to interact with any code.

