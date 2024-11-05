# Test-Driven Development Notes
### Costs of Developing Software include:
- Ananlysis (5%)
- Design (5%)
- Development (5%)
- Testing (10%)
- Integration (10%)
- Maintenance (65%)
> ### Agile vs. Waterfall
> - Project Management Methodologies
>    - Waterfall: Linear approach based on the costs/phases above.
>    - Agile: Cost cycle is compressed into smaller, faster cycles (focused on iterative development & delivering value).
### Fun Fact:
- Very high percentage of the cost of software can be accredited to software *maintenance*.
  - Impacts on Maintenance: Code Entrophy, Isolated Ownership, Infrequent Validation.
  - These challenges are associated with *Legacy Code*.
 - Test-driven development aims to reduce these costs, as well as enable building of higher quality software.
## Test-Driven Development
- Test: Procedure for verifying quality, performance, reliabilty, functionality of code (primarily before release and overall use).
- Tests verify:
  - Satifaction of requirements
  - Responds correctly to input
  - Acceptable performance and reliability
### What is Test-Driven Development?
- A software development process that relies on the repetition of a very short development cycle: requirements are turned into very specific test cases, then the software is improved to pass the new tests, only.
- **Red -> Green -> Refactor**
  - **Red**: Write test that fails.
  - **Green**: Minimal coding effort to create passing test.
  - **Refactor**: Clean up code, making sure test passes after each change.
### Benefits
- Encourages business benefits such as: requirement verification, regression catching, lower maintenance costs
- Developer benefits: design-first mentality, over-engineering prevention, increasing developer momentum
- Focus on needs of customer (delivering value)
## Types of Testing
- Units of Computation of Software: Classes, Functions, Dependencies
- There are *several* types of tests. Three primary testing types utilized are:
  - Unit Testing: verifies *each* unit is behaving properly *in isolation*.
  - Integration Testing: verifies *composition* of units are behaving properly *together*.
  - Acceptance Testing: verifies software (*complete application*) from user's POV.
- All testing types are important and have different purposes (strengths & weaknesses)
- **Great testing strategy** -> balance of **all** testing types.
- Black Box Testing vs. White Box Testing (*Testing Styles*)
  - **Black Box Tests**
    - Views component without insight into the component
    - Cannot reach inside component to verify what is happening with it.
    - Aims to verify behavior of software by giving different inputs & only observing output.
    - Pro: Testing from outside, internals are able to change without impacting tests.
    - Con: More dependencies, more difficulty to test without proper isolation.
  - **White Box Tests**
    - Allows for the ability to monitor communication happening within component itself.
    - Ability to inject test-specific dependencies for the component to communicate with (vs real-world dependencies assumed)
    - Pro: Powerful technique for testing systems with lots of dependencies & interconnected components.
    - Con: More invasive, hence test focuses more on *how* it works versus *if* it's working correctly. Sensitive and can even damage tests with change.
## Testing Frameworks & Tools
- xUnit Frameworks (Unit Testing)
  - SUnit (Smalltalk) [parent of unit testing frameworks]
  - JUnit (Java) [descendant of SUit]
  - Others include: NUnit, xUnit.net (.NET); RUnit (Ruby); CppUnit (C++); py.test (Python); Mocha (Javascript); AVA (Node.js);  etc.
- User Interface Frameworks (Acceptance Testing)
  - Selenium, Watir
  - cypress.io
  - Visual Studio Coded UI Test (Microsoft)
  - Test Studio (Telerik)
  - Silk Test (Micro Focus)
## Testing Concepts
- Test(s) -> Test Suite(s)
- **Before/After Hooks**
  - Building blocks for tests: BeforeEach, Test, AfterEach
  - Building blocks for test suites: Before, Test Suit, After
### Arrange/Given -> expected -> Act/When/actual -> Assert/Then**
- Verification Concepts:
  - **Assert**: allows us to tell the test what values we expect, mechanism that determines test passing/failing.
- Test Execution:
  - Tests are executed using **Test Runner**
  - Test Runner can be built into testing framework; can also be it's own framework.
  - Synchronously vs. Asynchronously : One at a time vs. At the same time(parallel).
  - Test isolation will make for tests to work for both.
## Testing Techniques
- **Dependency Injection**: a technique whereby on object supplies the dependencies of another object.
  - Dependency: Objects used by another object.
  - Injection: Action to provide the dependency to object that needs to use it.
- DI Mechanisms:
  - Constructor (or Method) Injection: Provides dependencies through a class constructor or method. Constructor[OOP], Method[Non-OOP]
  - Property/Setter Injection: Using a property/attribute or setter method to inject dependencies.
- DI Trade-offs:
  - Self-contained code -> Easier to understand, harder to test
  - Dependency-injected code -> Harder to understand, easier to test.
- **Test Double**: term for any object used during a test to replace a real object with a test specific object.
- TD Types:
  - Stubs: Provides canned answers when certain methods/properties are called during test.
  - Mocks: Provides specific answers and pre-programmed with expectations & assertions that are verified after a test is run.
  - Others include: Fakes, Spies, etc.
## Things to Avoid (Anti-Patterns)
- Dependencies between Tests
  - Order of tests should NOT matter
  - Cascading failures can be difficult to track down
  - Tests should work regardless of serial vs. parallel execution
- Testing Implementation Details
  - Focus on **what** is trying to be solved, not **how** it's being solved
- Long-Running Tests
  - *Warning sign* that code might be too coupled
  - *Warning sign* that code might not be very testable
## Limitations
- Possible holes in tests
- TDD is not sufficient by itself (account for: deployment verification, network changes, integration issues, etc.)
- Management buy-in AND support is **vital**
## As a developer, consider this:
- **How is my software performing?** (Performance Testing)
- **Is my production software behaving?** (Production Testing)
- **Is my software secure?** (Security and Compliance Testing)
