# State Machine Diagram

## 1. Diagram Title
**AI-Powered University Helpdesk Chatbot - Conversation Request Lifecycle**

## 2. Purpose
This diagram models the lifecycle and state transitions of a single chatbot conversation/request from the perspective of the system backend. It is essential for understanding how the system handles asynchronous API calls and maintains session context.

## 3. Entities Involved
The individual Chat Request / Active Session.

## 4. UML Diagram

```mermaid
stateDiagram-v2
    [*] --> Idle: System Ready
    
    Idle --> QuestionEntered: Student submits query
    
    QuestionEntered --> QueryProcessing: Begin NLP parsing
    
    QueryProcessing --> KnowledgeRetrieval: Intent extracted
    
    KnowledgeRetrieval --> ResponseGeneration: Relevant data found
    KnowledgeRetrieval --> FallbackResponse: No relevant data found
    
    ResponseGeneration --> ResponseDisplayed: Answer formulated
    FallbackResponse --> ResponseDisplayed: Fallback formulated
    
    ResponseDisplayed --> FeedbackSubmitted: Student clicks rating
    ResponseDisplayed --> SessionEnded: User closes chat / Timeout
    FeedbackSubmitted --> SessionEnded: Feedback recorded
    
    SessionEnded --> [*]
    
    %% Allow subsequent questions in same session
    ResponseDisplayed --> QuestionEntered: Student asks follow-up
    FeedbackSubmitted --> QuestionEntered: Student asks follow-up
```

## 5. Short Explanation
The system starts in an `Idle` state. Upon receiving a query, it transitions sequentially through `QueryProcessing` and `KnowledgeRetrieval`. Depending on the retrieval success, it enters either `ResponseGeneration` or `FallbackResponse`. Once the text is prepared, the state moves to `ResponseDisplayed`. From here, the user may trigger a `FeedbackSubmitted` state, end the session (`SessionEnded`), or enter a new question, looping the system back to `QuestionEntered` to maintain context.
