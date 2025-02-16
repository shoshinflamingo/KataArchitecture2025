# Allow candidates to appeal a small set of questions

## Context and Problem Statement

An unfair grading can ruin a career. We want to be sure to have feedback channels to detect any potential issue.

## Decision Drivers (Why)

* Data integrity: grading accuracy
* Scalability: grading requires non-scalable human intervention
* Observability: need to evaluate the AI grading

## Considered Options

* AI as a judge[^1]
* Manually sample AI results
* Allow candidates to appeal

## Decision Outcome

Decided to allow candidates to appeal a small set of questions because to provide a feedback
mechanism without overloading our experts.

AI as a judge can be used in other parts of the system but may not be precise enough.

Manually sampling has the advantage of not involving the customer. However, sampling requires too much manual work
from our experts.

In the appeal web form we can ask to select the type of problem:

* Misleading or ambiguous question
* Grading doesn't match explanation
* Explanation considered wrong.
* Other
  We should always allow a text section.

## Consequences (Trade-Offs)

* Good,
    * We can also get feedback about ambiguous or misleading questions.
    * Candidates would feel more confident in the grading process.
    * Will help with the `Analysis Service`.
    * Any accepted appeal can be used to implement Reinforcement learning from human feedback (RLHF).
    * We have a business metric for the grading process.
* Bad,
    * If a lot of appeals are right, this may damage the trust in us. (But better to know it early and fix it)
    * Failed candidates tend to appeal just in case. (we could charge a small amount to avoid this and return any
      paid amount or even double it if the appeal is right.)

[^1] See:

* [Thought works radar](https://www.thoughtworks.com/en-us/radar/techniques/llm-as-a-judge)
* [AI Engineering, Chip Huyen: Chapter 3, section AI as a judge](https://learning.oreilly.com/library/view/ai-engineering/9781098166298/ch03.html#ch03a_ai_as_a_judge_1730150757064706)