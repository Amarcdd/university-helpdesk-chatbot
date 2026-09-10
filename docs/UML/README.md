# Purpose of the UML Folder

This directory (`docs/UML`) contains professional UML (Unified Modeling Language) diagram documentation for the AI-Powered University Helpdesk Chatbot project. These diagrams provide a visual representation of the system's requirements, structure, behavior, and deployment environment, acting as a crucial bridge between the text-based Software Requirements Specification (SRS) and the technical design and implementation phases.

## List of All Diagrams

1. **[Use Case Diagram](Use_Case_Diagram.md)** - Visualizes the interactions between the system's actors (Student and Administrator) and the chatbot system's features.
2. **[Class Diagram](Class_Diagram.md)** - Depicts the conceptual domain model, showing the primary objects/classes within the system, their attributes, methods, and the relationships between them.
3. **[Sequence Diagram](Sequence_Diagram.md)** - Details the chronological sequence of interactions between system components during both student queries and administrator operations.
4. **[Activity Diagram](Activity_Diagram.md)** - Maps the step-by-step workflow of processing a student's question, including decision points for fallback handling.
5. **[State Machine Diagram](State_Diagram.md)** - Illustrates the lifecycle and state transitions of a student's question and the overall chatbot session.
6. **[Component Diagram](Component_Diagram.md)** - Outlines the major logical components of the software architecture and their interfaces/dependencies.
7. **[Deployment Diagram](Deployment_Diagram.md)** - Provides a technology-neutral mapping of the software components onto physical or logical hardware nodes.

## Relationship of Diagrams to the SRS

Every diagram in this folder is strictly derived from the existing `Requirement_Report.md` and `SRS.md` documents. 
- The **Use Case Diagram** directly corresponds to the Functional Requirements (FR-01 to FR-10) and Section 3 (System Features).
- The **Class Diagram** represents the entities identified in Section 7 (Data Requirements).
- The **Activity and Sequence Diagrams** illustrate the "Main Flow" and "Alternative/Exception Flow" detailed in Section 3 of the SRS.
- The **Deployment Diagram** reflects Section 2.4 (Operating Environment) and Section 14 (Hardware Requirements).

No unsupported features, actors, or enterprise-scale assumptions have been introduced.

## Value of Each Diagram in a Viva / Practical Submission

- **Use Case Diagram:** Useful for quickly proving to an examiner that all project scope requirements and actor responsibilities have been accounted for.
- **Class Diagram:** Demonstrates a fundamental understanding of Object-Oriented Design (OOD) principles, showing how real-world requirements translate into data structures.
- **Sequence Diagram:** Excellent for explaining *how* the NLP and AI generation work chronologically without getting bogged down in code.
- **Activity Diagram:** Ideal for showing logical flow, specifically proving that the system has proper error handling and fallback logic (a key requirement).
- **State Machine Diagram:** Proves that the developer understands the lifecycle of a request, which is vital for asynchronous or API-dependent processes like AI generation.
- **Component & Deployment Diagrams:** Show architectural maturity, demonstrating how the system is logically decoupled and physically deployed over a client-server architecture.
