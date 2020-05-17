---
layout: page
title: Unit Tests
nav_order: 4
has_children: true
permalink: /unit-tests/home
---


<!-- - [Backend](backend) -->
<!-- - [Frontend](frontend) -->




## What is a Unit Test?

> A unit test is an automated piece of code that invokes the unit of work being tested, and then checks some assumptions about a single end result of that unit. A unit test is almost always written using a unit testing framework. It can be written easily and runs quickly. It’s trustworthy, readable, and maintainable. It’s consistent in its results as long as production code hasn’t changed.

-- Roy Osherove, The Art of Unit Testing (2nd Edition)


## **Unit** in Unit Tests

Unit tests are focused on testing a small(est) part of the software system. They are usually isolated from other components and should allow us to verify correctness of individual parts. The execution time of a unit test should be relatively faster than other forms of automated tests such as integration testing.


## A First Example

Unit testing frameworks are available to help in test code organization and execution. 

Most frameworks provide users ways to express test specifications and group related test specifications into test suites. 

### With JavaScript (jasmine)

*Example taken from [Jasmine docs](https://jasmine.github.io/2.0/introduction.html)*

```
describe("A suite", function() { // #1
  it("contains spec with an expectation", function() { // #2
    expect(1 + 1).toBe(2); // #3
  });
});
```

For the Jasmine framework, test specifications are written by calling the `it()` function (`#2`) and the expectations stated within the function (`#3`). The `describe()` function is for grouping related test specs.

## Characteristics of Good Unit Tests

> Unit tests must be trustworthy, readable, maintainable. 

Unit tests are pieces of codes that will be written and maintained by developers and thus should garner the same care as system code. Just as with system codes, developers can rely on principles and (better) practices to write clear test codes. 

Fast
: Develoeprs use unit tests to get immediate feedback to decide on a course of action. If tests are slow, feedback on whether new bugs were introduced will be delayed and will slow down developers.

Repeatable
: A test is trustworthy if it produces the same result every time it is executed. Tests should provide reassurance that when all tests passed, then no bugs have been introduced to the system. To achieve this, tests should not rely on external and volatile external states.

Isolated
: Tests should have full control of the unit under test. Isolation gives better indication as to the source of an error which helps developers to easily pinpoint problems.

Does Correct Checks
: Make sure that the assertions / expectations placed in unit tests verify the expected state / output of the unit being tested.

## Best Practices

Maintain tests with code
: when there are code changes, there should be unit test changes as well. When a bug is found in the system, write a new test specification along with the fix to the bug. 

Structure test codes by Arrange -> Act -> Assert
: Structure the unit test specification by 
- setting up the code under test by preparing the dependencies (use mocks / stubs if needed) and the data that will be used
- executing the unit under test
- verifying the expectations through assertions

```
it("can have more than one expectation", function() {
    // Arrange
    const foo = createFoo(); 
    
    // Act
    const result = foo.bar();

    // Assert
    expect(result).toEqual(1);
});
```

Agree on Test Source Code Organization and Names
: For example,
- One test file per component / service / others being tested (`abc.component.ts` and `abc.component.spec.ts`)
- `describe()` as component name
- test spec name should follow `should <expected behavior> when <state>` (`it('should return sum when 2 integers are passed in')`)


Avoid test interdependence
: Each test should manage its own set up and cleaning up of data. Avoid reusing data produced by one test spec into another test spec. For example, test 2 using record created by test 1. If test 1 fails, data will not be creatd and test 2 will also fail.


Verify a single use case per test spec
: There should ideally be one assertion per test spec to test a single state change or output. If an assertion fails, test will alrady be marked as failed and all succeeding assertions will not be executed anymore. An execption to this is if attributes of a single state is being asserted. For example when sending emails and testing the `sendTo` and `cc` attributes where it doesn't make sense to continue on checking the other attributes when one has already failed.


Avoid logics in tests (if, while)
: This usually indicates that the test spec is testing too much. Tests with if logic can usually be separated into multiple tests. 


Only use setup (or `beforeEach` / `before`) and teardown (or `afterEach` / `after`) functions when logically
: When setting up multiple units under test within a test suite and when only needing to tweak some attributes / parameters, consider creating a creation method and manully calling this method instead of using setup and teardown functions. Practice applying the DRY principle even in test code.


## Tips, Tricks, and Others

### Mocks and Stubs

Reduce dependenc on external system by using mocks and stubs. Most unit testing frameworks provide ways to easily create a stub. 

- Stub - replaces a dependency such that the program will run properly
- Mock - a stub that’s asserted against

> An external dependency is an object in your system that your code under test interacts with and over which you have no control. (Common examples are filesystems, threads, memory, time, and so on.

> A stub is a controllable replacement for an existing dependency (or collaborator) in the system. By using a stub, you can test your code without dealing with the dependency directly.

For more information about mocks and stubs, please check [Test Doubles — Fakes, Mocks and Stubs](https://blog.pragmatists.com/test-doubles-fakes-mocks-and-stubs-1a7491dfa3da).