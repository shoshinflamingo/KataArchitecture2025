```mermaid
sequenceDiagram
    actor Expert
    participant AMG as Aptitude Manual Grader
    participant ASAVA as AI Short Answer Verification Agent
    Expert->>AMG: Get short answers
    AMG->>ASAVA: Analize the short answers
    ASAVA-->>AMG: Return highlights
    AMG-->>Expert: Return enriched response
    Expert->>ASAVA: Provide feedback for highlight
    ASAVA->>ASAVA: Learn
```