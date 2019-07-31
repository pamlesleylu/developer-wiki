# Frontend Unit Tests

The Angular Testing library will be used to initialize angular-related test fixtures such as components and services. Jest will be used as the test runner, the assertion library and the mocking library.

To run the frontend unit tests, execute `ng test lead-generation`

### References
- https://blog.nrwl.io/nrwl-nx-6-3-faster-testing-with-jest-20a8ddb5064
- https://vsavkin.com/three-ways-to-test-angular-2-components-dcea8e90bd8d
- https://angular.io/guide/testing
- https://jestjs.io/

# Backend Unit Tests

## Services

`sqllite3` is used to test backend interaction with the DB via sequelize. The `apps/api/test/` directory contains several utility functions to start up the connection to the in-memory database and to seed records in the database. 

It is imperative that all imports of sequelize models in your code should use the fully qualified path (i.e., instead of `./account.entity`, use `@api/models/accounts/account.entity`). This is so that the sequelize library used in testing will be able to find the models that will be added to it when a DB connection is started.

Do not change the data in the seed files. This might break unit tests using these data.