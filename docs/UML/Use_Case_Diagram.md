# Use Case Diagram

## 1. Diagram Title
**AI-Powered University Helpdesk Chatbot - Use Case Diagram**

## 2. Purpose
This diagram illustrates the primary interactions between external actors and the chatbot system. It visually represents the major functional requirements extracted from the SRS, including knowledge retrieval, query processing, fallback handling, and administrative management.

## 3. Actors Involved
- **Student**: The primary end-user seeking university information.
- **Administrator**: The university staff member managing the system.

## 4. UML Diagram

```mermaid
flowchart LR
    %% Actors
    Student((Student))
    Admin((Administrator))

    %% System Boundary
    subgraph Chatbot System
        Access[Access Chatbot]
        Ask[Ask Question]
        Process[Process Natural Language Query]
        Retrieve[Retrieve Knowledge]
        Generate[Generate Answer]
        Fallback[Receive Fallback Response]
        History[View Conversation History]
        Feedback[Submit Feedback]
        
        Login[Administrator Login]
        Manage[Manage Knowledge Base]
        Add[Add Information]
        Update[Update Information]
        Delete[Delete Information]
        Monitor[Monitor Usage]
    end

    %% Student Relationships
    Student --> Access
    Student --> Ask
    Student --> History
    Student --> Feedback

    %% Include and Extend Relationships for Query Processing
    Ask -. "<<include>>" .-> Process
    Process -. "<<include>>" .-> Retrieve
    Retrieve -. "<<include>>" .-> Generate
    Retrieve -. "<<extend>> \n (If info not found)" .-> Fallback

    %% Administrator Relationships
    Admin --> Login
    Admin --> Manage
    Admin --> Monitor

    %% Include Relationships for Knowledge Management
    Manage -. "<<include>>" .-> Add
    Manage -. "<<include>>" .-> Update
    Manage -. "<<include>>" .-> Delete

    %% Precondition Relationship
    Manage -. "<<include>> \n (Requires Auth)" .-> Login
    Monitor -. "<<include>> \n (Requires Auth)" .-> Login

```

## 5. Short Explanation
The Student actor interacts with the system to ask questions, view history, and submit feedback. The process of asking a question inherently includes processing the natural language, retrieving knowledge, and generating an answer. If the knowledge is missing, the system extends the retrieve function to provide a fallback response. The Administrator actor must log in to monitor usage or manage the knowledge base, which involves adding, updating, or deleting university information.
