# Use separated components for AI tasks

## Context and Problem Statement

Based on our `AI opportunities`, we identified four AI potential responsibilities:

* Short question AI grader
* Use case grade analyzer
* AI Pattern analyzer
* Quiz variant generator

We could include them in common components or separate them in their own components.

| AI responsibilities      | Potential component               |
|--------------------------|-----------------------------------|
| Short question AI grader | Aptitude Manual Grader            |
| Use case grade analyzer  | Architecture Manual Grader        |
| AI Pattern analyzer      | Aptitude Test Analysis Service    |
| Quiz variant generator   | Aptitude Test Maintenance Service |

## Decision Drivers (Why)

We use the granularity
drivers [Software Architecture: The hard parts chapter 7](https://learning.oreilly.com/library/view/software-architecture-the/9781492086888/ch07.html)

### Disintegrators

| Driver                     |                                                                        | 
|----------------------------|------------------------------------------------------------------------|
| Service scope and function | Yes, doing too many things. AI is complex enough                       |
| Code volatility            | Yes, AI changes and the other components change for different reasons  |
| Scalability and throughput | Yes, AI components can wait some time to produce reports.              |
| Fault tolerance            | Yes, AI components may fail and re-analyze later                       |
| Security                   | Somehow. AI components won't have any connection to the external world |
| Extensibility              | Not sure. Very difficult to predict AI.                                |

### Integrators

| Driver                    |                                                          | 
|---------------------------|----------------------------------------------------------|
| Database transactions     | No                                                       |
| Workflow and choreography | No. They may call other database replica                 |
| Shared code               | No                                                       |
| Database relationships    | Partially yest. Some data will be shared by one service. |

## Considered Options

* Join with other components
* Create AI separated components

**Note**: we could have a different ADR per component but the drivers are very similar for all. 

## Decision Outcome

We chose to create AI separated components because:

* 4.5 disintegrators
* 0.5 integrators

We have a conflict between our three key characteristics: Separated components worsen the `Data Integrity` but improve
the `Scalability` and `Availability`.

* `Data Integrity` is still very feasible because candidates can't alter their test submissions.
* We really do not want to worsen the grading experience of our costly designated experts.

Also:

* Consistent with our current microservice architecture (`Conceptual consistency`)
* AI tasks tend to be executed in specialized hardware (`Performance`, `costs`). There are specific cloud instances
  types or solutions optimized to reduce the cost.

## Consequences (Trade-Offs)

* Good
    * Can deploy some AI submodules as cloud services (AWS Bedrock, Google Vertex AI, Azure Cognitive Services)
    * AI tasks won't affect the availability or responsiveness of any component used by valued designated experts
    * Separate teams can work on AI tasks (`feasibility`)
    * API gateway won't connect those AI components (`Security`)

* Bad
    * Redundant data between databases: E.g., Submission ungraded and Architecture Pre-graded AI
    * `Data integrity`. No Foreign key constraints between databases.
