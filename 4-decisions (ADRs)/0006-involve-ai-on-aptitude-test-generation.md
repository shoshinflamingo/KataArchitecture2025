# Involve AI on Aptitude Test Generation

## Context and Problem Statement

Certifiable, Inc. is experiencing a surge in certification requests and must ensure that aptitude tests remain both challenging and current. Manual question creation is increasingly unsustainable, and there is a critical need for dynamic, unpredictable test content that reflects the latest industry practices. Moreover, preventing candidates from memorizing questions over multiple test cycles is paramount for maintaining the integrity of the certification process.

## Decision Drivers (Why)

* **Content Freshness:** Generate questions that incorporate current trends and best practices in software architecture.
* **Test Integrity:** Prevent question memorization by dynamically rephrasing and shuffling existing content.
* **Scalability:** Efficiently handle a higher volume of test requests without over-relying on manual processes.
* **Efficiency:** Reduce manual workload by automating question generation while still leveraging expert validation.
* **Quality Assurance:** Ensure that every generated question meets high standards through expert review.

## Considered Options

* **Manual Test Creation:** Continue to rely solely on experts to create and update questions.
* **Algorithmic Randomization:** Use basic random shuffling techniques to vary question presentation.
* **AI-based Test Generation (Chosen Option):** Integrate AI components to generate and shuffle high-quality test questions.

## Decision Outcome

**Chosen option:** "AI-based Test Generation for the Aptitude Test Generator Service," because it provides a robust, scalable solution that continuously produces fresh, relevant, and unpredictable test content. This approach meets the need for dynamic question generation while preserving the high quality ensured by expert validation.

## Consequences (Trade-Offs)

* **Good,** because the AI generates up-to-date and varied test content, reducing manual workload.
* **Good,** because it scales effectively with the increasing demand for certifications.
* **Bad,** because initial integration of AI components may involve higher upfront costs.
* **Bad,** because the system relies on expert validation to catch occasional inaccuracies, introducing additional review steps.

## Pros and Cons of the Options

### Manual Test Creation

* **Good,** ensures high quality and expert-driven relevance.
* **Bad,** is time-consuming and does not scale with growing demand.

### Algorithmic Randomization

* **Good,** is a low-cost method to vary test content.
* **Bad,** lacks the depth and contextual relevance provided by advanced AI generation.

### AI-based Test Generation

* **Good,** continuously produces fresh, relevant questions aligned with current industry trends.
* **Good,** reduces manual effort and supports scalability.
* **Bad,** introduces complexity and requires robust expert validation.
* **Bad,** entails a higher initial investment compared to simpler methods.

## More Information

This decision aligns with Certifiable, Inc.'s strategic goals to scale operations, maintain test integrity, and ensure the highest quality of certification exams. The AI-based Test Aptitude Generator Service will be continuously monitored and refined through expert feedback, ensuring it adapts to evolving industry standards and growing certification demands.
