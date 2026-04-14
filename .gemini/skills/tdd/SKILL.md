---
name: tdd
description: Implements a strict test-driven development (TDD) workflow. Use this for any software development task, such as implementing new features, bug fixes, or refactoring.
---

# Test-Driven Development Workflow

You must strictly enforce the TDD lifecycle. Do not move to the next phase without explicit direction from the human.

## 1. Preparation (Test List)
Before writing any code, the behaviors to implement must be identified.
- **Behavioral Decomposition**: Help break high-level behaviors down into smaller, testable sub-behaviors.
- **Test Case Identification**: List basic cases and edge cases.
- **Collaboration**: Wait for the human to define this list, or help them structure it if requested. Do not proceed until the test list is locked.

## 2. Red Phase (Write a Test)
- **Pick One**: Focus on exactly one item from the Test List.
- **Design Backward**: Start with the assertion.
- **Write Test**: Write the test code exactly as instructed by the human.
- **Verify Failure**: Ensure the test runner is executed and verify the test fails for the expected reason.

## 3. Green Phase (Make It Pass)
- **Minimal Code**: Use the "Fake It" strategy (e.g., return a constant). Do not implement the "real" logic yet unless it's simpler than faking it or explicitly requested by the human.
- **Write Implementation**: Write the minimal change as instructed.
- **Verify Success**: Run the tests.
- **Coverage Check**: If branch coverage decreases compared to the previous run, the test run is considered **failed** (over-engineering alert). Ask the human how to simplify the implementation to pass the test with higher coverage.

## 4. Refactor Phase (Make It Right)
- **Prompt for Refactor**: Ask the human: "Would you like to refactor the current implementation, or move to the next test?"
- **Identify Code Smells**: If you noticed code smells (duplication, bad naming, unnecessary complexity) during the Green phase, point them out now as suggestions for the Refactor phase.
- **Verify**: Run tests after any refactor to ensure coverage and passing status are maintained.

## 5. Repeat
- Cross off the item from the Test List and return to the Red Phase for the next item.
