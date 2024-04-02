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
- `TestCase` uses the Template Method pattern through the `runBare()` method, which outlines the structure of executing a test.
- This method calls `setUp()` to set up the test environment, `runTest()` to execute the test, and `tearDown()` to clean up after the test.
- Subclasses of `TestCase` can override `setUp()` and `tearDown()` to provide specific behaviors while maintaining the overall test execution structure.

### Extensibility
- New test cases can be created by extending `TestCase` and overriding necessary methods, allowing for custom setup and teardown processes while reusing the overall test execution algorithm.

## 1. Composite Pattern

### Relevant Classes/Interfaces
- `Test`: The component interface.
- `TestCase`: Leaf in the composite structure representing individual tests.
- `TestSuite`: Composite class that can contain `TestCase` or other `TestSuite` objects.

### Collaboration and Functioning
- `Test` provides the common interface for individual tests and test suites, with methods like `countTestCases()` and `run(TestResult result)`.
- `TestCase` implements `Test` and represents a single test.
- `TestSuite` aggregates multiple `Test` instances, handling them uniformly. When `run()` is called on a `TestSuite`, it delegates the call to each of its `Test` instances.

### Extensibility
- New test types can be easily added by implementing the `Test` interface, demonstrating the flexibility and scalability of the Composite pattern.

## 3. Strategy Pattern

### Relevant Classes/Interfaces
- `TestResult`: Context in the Strategy pattern.
- `Protectable`: Strategy interface.

### Collaboration and Functioning
- `TestResult` uses `Protectable` strategies to run test code. The `runProtected()` method in `TestResult` accepts a `Protectable` object, allowing different test execution behaviors to be encapsulated within `Protectable` implementations.
- `Protectable` provides a single method `protect()` that encapsulates the test execution logic.

### Extensibility
- Different test execution behaviors can be introduced by implementing new `Protectable` strategies, offering flexibility in how test code is executed within the `TestResult` context.


