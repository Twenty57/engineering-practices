# Automated Tests

## Introduction

The goal of writing and running tests is to reduce the cost of building and maintaining software. Good tests do this by

- Preventing bugs from reaching production. A bug is much more expensive to fix in production than during development.
- Allowing developers to make changes faster. Tests give developers confidence that the code is working as expected. It also acts as documentation helping developers understand the code.

## Principles

- Automated. Tests should run without human intervention.
- Behavioral. Test behavior, not implementation details.
- Isolated. Tests should return the same result regardless of the order in which they run.
- Fast. Tests should run quickly.
- Repeatable. The same test should always yield the same results.
- Comprehensible. Readers of a test should understand why it's there and how it works.
- Specific. If a test fails, the cause of the failure should be obvious.

## Best practices

- Name tests [Name]\_[Scenario]_[ExpectedBehavior], like `CreateUser_WithNoName_Fails`. It explicitly expresses the intent of the test, which acts like documentation and makes it possible to infer the behavior of the code without looking at the code itself.
- Structure the internals of tests using the Arrange, Act, Assert pattern. This improves readability by clearly highlighting dependencies and assertions:
    - Arrange variables, create and set them up as necessary.
    - Act. Call the functions to enact the behavior under test.
    - Assert that something is as expected.
- Use the simplest possible input to verify the behavior. This improves resilience to code changes.
- Consider using helper methods instead of setup and teardown. Helper methods may improve readability and reduce unwanted dependencies between tests.

## Accreditation
The guidelines in this document are largely based on our own experience but more eloquently expressed by: 
- <https://kentbeck.github.io/TestDesiderata/>
- <https://learn.microsoft.com/en-us/dotnet/core/testing/unit-testing-best-practices>