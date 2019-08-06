---
layout: default
title: Backend Unit Tests
parent: Unit Tests
nav_order: 3
---
# Backend Unit Tests

To run the backend unit tests, execute `ng test api`

## Controllers

TODO

## Services

`sqllite3` is used to test backend interaction with the DB via sequelize. The `apps/api/test/` directory contains several utility functions to start up the connection to the in-memory database and to seed records in the database. 

It is imperative that all imports of sequelize models in your code should use the fully qualified path (i.e., instead of `./account.entity`, use `@api/models/accounts/account.entity`). This is so that the sequelize library used in testing will be able to find the models that will be added to it when a DB connection is started.

Do not change the data in the seed files. This might break unit tests using these data.