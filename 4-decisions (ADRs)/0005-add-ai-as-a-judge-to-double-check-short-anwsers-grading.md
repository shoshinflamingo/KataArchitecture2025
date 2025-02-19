# Add `AI as a judge` to double-check the grading of short answers.

## Context and Problem Statement

We need to evaluate the performance of our `Short Answer AI Grader`. Other components can be manually reviewed, but we 
aspire to have fully AI graded short questions.
At least for a high percentage of answers.

## Decision Drivers (Why)

* Data integrity: grading accuracy
* Scalability: grading requires non-scalable human intervention
* Observability: need to evaluate the AI grading

## Considered Options

* Manual evaluation
* AI as a judge
* Use old data to evaluate

## Decision Outcome

We decided to use `AI as a judge` to evaluate the performance of our `Short Answer AI Grader` because

* Our objective is to save time and work with AI. Manual sampling would require a lot of verifications from experts.
* Old data could be an initial approach but would not work with any future test and can get obsolete. Also, it prevents
us from using this information to improve our AI.
  (Evaluating a model with the data that has been trained is like repeating last year's test for the final exam)
  

## Consequences (Trade-Offs)

* Good:
    * `Data integrity` We have an extra filter to guarantee that the grading system works. 
    * `Scalabilty`: Allow us to tune the threshold for human review
    * `Observability`: Provides metrics that can be used in the `Aptitude Test Analysis Service`

* Bad:
    * `Complexity`: another AI component to deploy.
    * `Cost`: AI hardware or cloud hosting is expensive.