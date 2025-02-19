# Reuse manual grader for AI grading (renaming it to `Aptitude Grader`)

## Context and Problem Statement

Both manual and AI grading need to trigger `Grade consolidation`.

## Decision Drivers (Why)

* Simplicity
* Feasibility

## Considered Options

* Move `Grade consolidation` to its very own component
* Duplicate logic
* Reuse `Manual Grader` for AI grading (Chosen Option)

## Decision Outcome

Decided to reuse logic in `Manual Grader` for AI grading renaming as `Aptitude Grader` as a consequence.
Our AI subsystem can reuse the same API methods (Typically a REST, GraphQL, or gRPC API).
This reduces our development effort and ensures that any Short Answer logic is not duplicated.

## Consequences (Trade-Offs)

* Good:
    * Fewer components with connections to `Aptitude Test Ungraded Database` and `Aptitude Test Graded Database`
    * No effort to segregate the `Grade consolidation` logic into a new component
    * No duplicated logic
* Bad:
    * Need to rename the references in code, microservice endpoints, etc,
    * The `Aptitude Grader` may require some API endpoints optimized for the manual UI that will not be used by the AI
      subsystem. But that is OK