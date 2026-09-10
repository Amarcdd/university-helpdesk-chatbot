# Sequence Diagram

## 1. Diagram Title
**AI-Powered University Helpdesk Chatbot - Interaction Sequence Diagrams**

## 2. Purpose
This document presents two sequence diagrams: one detailing the chronological flow of a student asking a question (including normal response generation and fallback handling), and one showing the administrator login and knowledge base management process.

## 3. Actors/Components Involved
- **Actors**: Student, Administrator
- **System Components**: Chat Interface, Query Processor (NLP), Knowledge Base (DB), AI Generator, Admin Dashboard, Auth Service.

## 4. UML Diagrams

### Part 1: Student Question & Answer Sequence

```mermaid
sequenceDiagram
    actor Student
    participant Interface as Chat Interface
    participant NLP as Query Processor (NLP)
    participant KB as Knowledge Base
    participant AI as AI Generator

    Student->>Interface: 1. Enter question (natural language)
    activate Interface
    Interface->>NLP: 2. Send raw query text
    activate NLP
    NLP-->>Interface: 3. Acknowledge processing
    NLP->>KB: 4. Search with processed intent
    activate KB
    
    alt Relevant Information Found
        KB-->>NLP: 5a. Return matching knowledge items
        NLP->>AI: 6a. Send prompt + retrieved context
        activate AI
        AI-->>NLP: 7a. Return generated natural language answer
        deactivate AI
        NLP-->>Interface: 8a. Send finalized answer
    else No Relevant Information Found
        KB-->>NLP: 5b. Return empty result
        NLP->>AI: 6b. Request fallback message generation
        activate AI
        AI-->>NLP: 7b. Return standard fallback response
        deactivate AI
        NLP-->>Interface: 8b. Send fallback message
    end
    
    deactivate KB
    deactivate NLP
    Interface-->>Student: 9. Display response
    deactivate Interface
```

### Part 2: Administrator Management Sequence

```mermaid
sequenceDiagram
    actor Admin
    participant Dashboard as Admin Dashboard
    participant Auth as Auth Service
    participant KB as Knowledge Base

    Admin->>Dashboard: 1. Enter username and password
    activate Dashboard
    Dashboard->>Auth: 2. Request credential validation
    activate Auth
    
    alt Invalid Credentials
        Auth-->>Dashboard: 3a. Validation failed
        Dashboard-->>Admin: 4a. Display error message
    else Valid Credentials
        Auth-->>Dashboard: 3b. Validation successful (Token generated)
        Dashboard-->>Admin: 4b. Grant access to admin panel
    end
    deactivate Auth
    
    Admin->>Dashboard: 5. Submit new/updated university policy
    Dashboard->>KB: 6. Add/Update knowledge item
    activate KB
    KB-->>Dashboard: 7. Confirm successful update
    deactivate KB
    Dashboard-->>Admin: 8. Display success notification
    deactivate Dashboard
```

## 5. Short Explanation
The first sequence demonstrates the student workflow. The query processor coordinates the flow, first pinging the Knowledge Base. Based on whether the Knowledge Base returns relevant data, the system either tasks the AI Generator to formulate a factual answer or triggers the fallback protocol. 

The second sequence illustrates the administrator's workflow. The Admin must first securely authenticate via the Auth Service before being allowed to push new or updated documentation to the Knowledge Base.
