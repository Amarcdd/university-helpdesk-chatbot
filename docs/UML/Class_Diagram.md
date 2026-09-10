# Class Diagram

## 1. Diagram Title
**AI-Powered University Helpdesk Chatbot - Conceptual Class Diagram**

## 2. Purpose
This diagram models the conceptual entities, data structures, and relationships described in the SRS Data Requirements. It shows how the system logically organizes users, messages, the knowledge base, and administrative functionality.

## 3. Classes Involved
Student, Administrator, ChatSession, Message, Question, Response, Feedback, KnowledgeBase, KnowledgeItem, Authentication, Monitoring.

## 4. UML Diagram

```mermaid
classDiagram
    class User {
        <<abstract>>
    }
    
    class Student {
        +askQuestion(query: String)
        +viewHistory()
        +submitFeedback(rating: Boolean)
    }
    
    class Administrator {
        +username: String
        -passwordHash: String
        +login()
        +addInfo(data: String)
        +updateInfo(data: String)
        +deleteInfo(id: String)
        +viewMetrics()
    }
    
    User <|-- Student
    User <|-- Administrator

    class ChatSession {
        +sessionId: String
        +startTime: DateTime
        +maintainContext()
    }
    
    class Message {
        <<abstract>>
        +timestamp: DateTime
        +content: String
    }
    
    class Question {
        +queryText: String
        +processNL()
    }
    
    class Response {
        +responseText: String
        +isFallback: Boolean
        +generate()
    }
    
    class Feedback {
        +isHelpful: Boolean
        +timestamp: DateTime
        +submit()
    }
    
    class KnowledgeBase {
        +search(query: String): List~KnowledgeItem~
        +add(item: KnowledgeItem)
        +update(item: KnowledgeItem)
        +delete(item: KnowledgeItem)
    }
    
    class KnowledgeItem {
        +id: String
        +category: String
        +content: String
        +lastUpdated: DateTime
    }
    
    class Authentication {
        +validateCredentials(user, pass): Boolean
        +createSession()
    }
    
    class Monitoring {
        +totalChats: Integer
        +popularTopics: List~String~
        +generateMetrics()
    }

    Student "1" -- "*" ChatSession : starts >
    ChatSession "1" *-- "*" Message : contains >
    Message <|-- Question
    Message <|-- Response
    Question "1" -- "1" Response : results in >
    Response "1" -- "0..1" Feedback : receives >
    
    Administrator "1" -- "*" KnowledgeItem : manages >
    Administrator "1" -- "1" Monitoring : views >
    Administrator "1" -- "1" Authentication : uses >
    
    KnowledgeBase "1" *-- "*" KnowledgeItem : stores >
    Question "*" -- "1" KnowledgeBase : queries >
```

## 5. Short Explanation
The diagram defines a base `User` class extended by `Student` and `Administrator`. A `Student` interacts through a `ChatSession`, which aggregates `Message` objects. Messages are specialized into `Question` and `Response`. A `Response` may optionally receive `Feedback`. The `Administrator` authenticates via the `Authentication` class, manages `KnowledgeItem` entities stored within the `KnowledgeBase`, and views usage via the `Monitoring` class. The design is kept language-neutral and purely conceptual.
