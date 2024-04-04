# Name: Praveen Singh
# Date: 04/01/2024
# Course: Spring 2024
# Assignment #: 5

# Design Patterns in JUnit 4

This document outlines the usage of various design patterns in the JUnit 4 project, a popular unit testing framework in Java. In this project, three design patterns have been identified and examined, with a focus on their functions, interoperability, and extensible possibilities.

## 1. Template Method Pattern

### Relevant Class
- `TestCase`

### Collaboration and Functioning
- The `runBare()` method in `TestCase` employs the Template Method pattern by outlining the steps involved in running a test.
- This function runs `runTest()` to run the test, `tearDown()` to clean up after the test, and `setUp()` to set up the test environment.
- `setUp()` and `tearDown()` can be overridden by `TestCase` subclasses to offer particular behaviours while preserving the general framework of test execution.

### Extensibility
- New test cases can be created by extending `TestCase` and overriding necessary methods, allowing for custom setup and teardown processes while reusing the overall test execution algorithm.

## 1. Composite Pattern

### Relevant Classes/Interfaces
- `Test`: Interface of the component.
- `TestCase`: The leaf that represents each particular test in the composite structure.
- The composite class `TestSuite` has the ability to hold `TestCase` and additional `TestSuite` objects.


### Collaboration and Functioning
- With functions like `countTestCases()` and `run(TestResult result)`, `Test` offers the common interface for individual tests and test suites.
- `TestCase` represents a single test that implements `Test`.
- `TestSuite` handles numerous `Test` instances consistently by aggregating them. A `TestSuite's` `run()` function assigns the call to each of its `Test` instances.


### Extensibility
- New test types can be easily added by implementing the `Test` interface, demonstrating the flexibility and scalability of the Composite pattern.

## 3. Strategy Pattern

### Relevant Classes/Interfaces
- `TestResult`: Context in the Strategy pattern.
- `Protectable`: Strategy interface.

### Collaboration and Functioning
- `TestResult` runs test code using `Protectable` techniques. `Protectable} objects are accepted by the `runProtected()` method in `TestResult}, which enables the encapsulation of various test execution behaviours within `Protectable` implementations.
- The test execution logic is contained in the single method `protect()` that `Protectable` offers.


### Extensibility
- Different test execution behaviors can be introduced by implementing new `Protectable` strategies, offering flexibility in how test code is executed within the `TestResult` context.


