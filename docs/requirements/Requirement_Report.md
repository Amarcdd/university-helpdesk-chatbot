# Software Requirements Specification
Requirement Report for
## AI Chatbot for University Helpdesk
IEEE-Style Requirements Document

Version 1.0

Prepared by
Aman Gupta - 202401100100035
Amar Dwivedi – 202401100100036
Abhishek Goswami – 202401100100011
Abhay Pratap singh – 202401100100006

KIET Deemed To Be University
Branch: Computer Science (CS) — B.Tech 3rd Year
September 2026

---

## Revision History
| Version | Date | Author | Reason for Change |
|---|---|---|---|
| 1.0 | September 2026 | Project Team | Initial IEEE-style requirement report including requirements elicitation, functional requirements, non functional requirements, business rules and analysis models. |

---

## Table of Contents
* 1. Introduction
  * 1.1 Purpose
  * 1.2 Document Conventions
  * 1.3 Intended Audience and Reading Suggestions
  * 1.4 Product Scope
  * 1.5 References
* 2. Overall Description
  * 2.1 Product Perspective
  * 2.2 Product Functions
  * 2.3 User Classes and Characteristics
  * 2.4 Operating Environment
  * 2.5 Design and Implementation Constraints
  * 2.6 User Documentation
  * 2.7 Assumptions and Dependencies
* 3. Requirements Elicitation
  * 3.1 Elicitation Objectives
  * 3.2 Stakeholders
  * 3.3 Elicitation Techniques
  * 3.4 Elicited Requirements
  * 3.5 Requirement Prioritization
  * 3.6 Requirement Validation
* 4. External Interface Requirements
  * 4.1 User Interfaces
  * 4.2 Hardware Interfaces
  * 4.3 Software Interfaces
  * 4.4 Communications Interfaces
* 5. Functional Requirements
  * 5.1 Authentication and Authorization
  * 5.2 University Knowledge Base Management
  * 5.3 Student Query and Conversation Management
  * 5.4 AI/NLP Response Generation
  * 5.5 Academic and Administrative Information
  * 5.6 Helpdesk Ticket and Escalation
  * 5.7 Notifications and Feedback
  * 5.8 Audit and Administration
* 6. Non-Functional Requirements
  * 6.1 Performance
  * 6.2 Safety
  * 6.3 Security and Privacy
  * 6.4 Usability
  * 6.5 Reliability
  * 6.6 Maintainability
  * 6.7 Scalability
  * 6.8 Traceability and Testability
* 7. Business Rules
* 8. Other Requirements
* Appendix A: Glossary
* Appendix B: Analysis Models
* Appendix C: To Be Determined List
* Requirement Report Summary

---

## 1. Introduction

### 1.1 Purpose
This Software Requirements Specification (SRS) defines the functional and non-functional requirements for an AI Chatbot for University Helpdesk. It specifies the system scope, stakeholders, interfaces, conversational workflows, university knowledge-base management, AI-assisted response generation, human escalation, ticket management, security expectations, constraints, and acceptance-oriented requirements for Version 1.0.

### 1.2 Document Conventions
Requirements use unique identifiers. FR identifies Functional Requirements, NFR identifies Non-Functional Requirements, and BR identifies Business Rules. Priority values are High, Medium, or Low. The words SHALL and MUST indicate mandatory behavior; SHOULD indicates a recommended behavior. Each requirement is intended to be clear, necessary, feasible and verifiable.

### 1.3 Intended Audience and Reading Suggestions
This document is intended for students, faculty/staff, helpdesk operators, administrators, project team members, project guides, developers, testers and reviewers. Readers should first review Sections 1–2 for context, Section 3 for requirement elicitation, Section 4 for interfaces, Sections 5–6 for detailed requirements, and Section 7 for business rules.

### 1.4 Product Scope
The AI Chatbot for University Helpdesk is a web-based conversational support system that provides a single point of access to approved university information. Users can ask natural-language questions about admissions, academics, examinations, fees, attendance, departments, campus services, schedules, policies and common helpdesk procedures. The system retrieves relevant approved information and generates concise responses. If a question is unsupported, ambiguous, low-confidence, or requires human action, the system can guide the user to a human helpdesk and create a tracked ticket.

### 1.5 References
* IEEE Software Requirements Specification template and organizational structure supplied as the project reference.
* University-approved notices, FAQs, policies, academic calendars, department information and helpdesk procedures.
* AI Chatbot for University Helpdesk UML and Data Flow Diagram documentation.
* Project implementation plan and feature specification.

---

## 2. Overall Description

### 2.1 Product Perspective
The AI Chatbot is a new self-contained university helpdesk web application. The planned architecture uses a React/Vite frontend, Node.js/Express backend, MongoDB for application data, a university knowledge base for approved content, an AI/NLP service for intent detection and response generation, and optional email/SMS/push notification services.

### 2.2 Product Functions
* University user authentication and role-based authorization.
* Natural-language chatbot interface and conversation history.
* University FAQ and knowledge-base retrieval.
* Intent detection and query classification.
* Grounded AI response generation using approved university context.
* Support for admissions, academics, examinations, fees, attendance, departments and campus services.
* Clarification handling for ambiguous queries.
* Human helpdesk escalation and ticket creation.
* Ticket status tracking and notifications.
* Response feedback and chatbot-quality analytics.
* Knowledge-base, user, ticket, category and configuration administration.
* Audit logging of important authentication, access, content and administrative events.

### 2.3 User Classes and Characteristics
| User Class | Main responsibilities |
|---|---|
| Student | Ask university questions, view answers, create/track helpdesk tickets and provide feedback. |
| Faculty / Staff | Ask academic and administrative questions and submit permitted service requests. |
| Helpdesk Operator | Review escalated queries, respond to tickets, update status and resolve user issues. |
| Administrator | Manage users/roles, knowledge-base content, categories, chatbot configuration, analytics and audit information. |
| Project Guide / Reviewer | Review requirements, workflows, traceability, diagrams, security and demonstrable functionality. |

### 2.4 Operating Environment
The system is intended to operate through modern desktop, laptop, tablet and smartphone web browsers. The planned server environment consists of Node.js/Express, MongoDB, REST APIs, a configured university knowledge base, an AI/NLP service, and optional notification services.

### 2.5 Design and Implementation Constraints
* MERN-oriented implementation is preferred for the academic project.
* Server-side authorization is mandatory for protected operations.
* Only authorized administrators may publish official university knowledge-base content.
* AI responses must be grounded in retrieved approved information where applicable.
* The chatbot SHALL NOT invent official fees, deadlines, policies, examination rules or institutional facts.
* Sensitive student information shall not be exposed to unauthorized users.
* External AI services may impose availability, rate, cost and data-handling constraints.
* Development and demonstrations should use synthetic data where real personal data is not required.

### 2.6 User Documentation
The project should provide concise instructions for login, asking questions, viewing sources, creating and tracking tickets, providing feedback, helpdesk operator workflows, and administrator knowledge-base management.

### 2.7 Assumptions and Dependencies
* Users have a supported browser and network connection.
* Approved university information is available in a maintained knowledge base.
* MongoDB is available for structured application data.
* AI/NLP service availability is required for AI-generated responses.
* Helpdesk staff are available for escalated requests.
* University policies and FAQs are maintained by authorized personnel.

---

## 3. Requirements Elicitation

### 3.1 Elicitation Objectives
Requirements elicitation is the process of identifying, collecting, clarifying and documenting what stakeholders need from the university helpdesk chatbot. The objectives are to identify stakeholder goals, understand common helpdesk problems, define required chatbot and ticket functions, identify security and privacy expectations, and convert stakeholder needs into testable requirements.

### 3.2 Stakeholders
| Stakeholder | Needs / Expectations | Priority |
|---|---|---|
| Student | Fast answers, simple language, accurate university information, ticket creation and status tracking. | High |
| Faculty / Staff | Reliable academic/administrative information and quick routing to responsible offices. | High |
| Helpdesk Operator | Clear escalated queries, conversation context, ticket queue and status management. | High |
| Administrator | User/role management, knowledge-base control, analytics and audit information. | High |
| Project Team | Implementable, testable, secure and maintainable requirements within academic scope. | High |
| Project Guide / Reviewer | Clear requirements, traceability, diagrams, security considerations and demonstrable functionality. | Medium |

### 3.3 Elicitation Techniques
| Technique | Application in Project | Expected Output |
|---|---|---|
| Stakeholder analysis | Identify students, faculty/staff, helpdesk operators, administrators and academic stakeholders. | Stakeholder needs and priorities. |
| Interviews / discussion | Discuss common questions, delays, repeated helpdesk requests and escalation problems. | User needs and workflow requirements. |
| Observation / workflow analysis | Model question-answer, clarification, ticket escalation and resolution workflows. | Process steps and system interactions. |
| Document analysis | Use university FAQs, notices, policies and the supplied IEEE-style SRS organization. | Structured requirements and source categories. |
| Use-case analysis | Describe login, ask question, view source, create ticket, respond to ticket and administer knowledge base. | Functional requirements and scenarios. |
| Requirement prioritization | Classify requirements by importance to the core helpdesk objective. | High/Medium/Low priorities. |
| Validation and review | Check requirements for consistency, necessity, clarity, feasibility and testability. | Approved/refined requirement set. |

### 3.4 Elicited Requirements
* Secure authentication and role-based access.
* Centralized approved university knowledge base.
* Natural-language question handling and intent classification.
* Context-aware conversational follow-up.
* Grounded AI responses with source/reference information where practical.
* Clarification and safe handling of unsupported or low-confidence questions.
* Helpdesk ticket creation, assignment, status tracking and escalation.
* Notifications for important ticket events.
* User feedback and chatbot-quality analytics.
* Audit logging, security, privacy, reliability and usability.

### 3.5 Requirement Prioritization
| Priority | Meaning | AI Chatbot Examples |
|---|---|---|
| High | Essential for a usable, secure and demonstrable system. | Authentication, query processing, knowledge retrieval, AI response, escalation, ticketing, security and audit. |
| Medium | Important supporting functionality. | Conversation history, notifications, feedback, analytics and convenience features. |
| Low | Optional enhancement that may be implemented later. | Advanced integrations, multilingual expansion and additional channels. |

### 3.6 Requirement Validation
* **Correct** — represents a genuine stakeholder or system need.
* **Unambiguous** — has only one reasonable interpretation.
* **Complete** — contains enough information to implement and test it.
* **Consistent** — does not conflict with another requirement.
* **Feasible** — can be implemented within the selected architecture and project scope.
* **Verifiable** — can be tested or inspected.
* **Traceable** — has a unique identifier and can be linked to a feature, workflow or analysis model.

---

## 4. External Interface Requirements

### 4.1 User Interfaces
The student/faculty interface shall provide login, chatbot dashboard, conversation area, suggested questions, knowledge/FAQ results, ticket creation, ticket status, notifications and profile areas. Helpdesk operators shall receive a ticket queue, ticket details, conversation context, response and status controls. Administrators shall receive user/role management, knowledge-base management, categories, configuration, analytics and audit screens.

### 4.2 Hardware Interfaces
No specialized hardware is required for Version 1.0. Standard computers, laptops, tablets and smartphones capable of running a supported web browser are sufficient.

### 4.3 Software Interfaces
| Software Component | Purpose |
|---|---|
| React / Vite | Frontend user interface and conversational chatbot experience. |
| Node.js / Express | REST API, business logic, authentication, authorization, tickets and administration. |
| MongoDB | Users, conversations, tickets, feedback, categories and configuration data. |
| University Knowledge Base | Approved FAQs, notices, policies, schedules, contacts and service information. |
| AI / NLP Service | Intent detection, contextual processing and response generation. |
| Notification Service | Email/SMS/push notifications for ticket and service events. |

### 4.4 Communications Interfaces
Frontend-backend communication shall use secure HTTP(S) REST APIs with JSON request/response data. AI, knowledge-base and notification integrations shall use protected connections and authenticated requests where supported.

---

## 5. Functional Requirements

### 5.1 Authentication and Authorization
Description and Priority: Authentication and Authorization. Priority: High.
Stimulus/Response Sequence: User opens portal → enters credentials → authentication → role/permission check → dashboard/chatbot.
* FR-01: The system shall provide secure login for supported university users.
* FR-02: The system shall enforce role-based authorization for student, faculty/staff, helpdesk operator and administrator functions.
* FR-03: Unauthorized requests shall be denied without exposing protected user, ticket or administrative data.
* FR-04: The system should maintain secure sessions and user profile information.

### 5.2 University Knowledge Base Management
Description and Priority: University Knowledge Base Management. Priority: High.
Stimulus/Response Sequence: Administrator creates/updates content → content is validated/published → chatbot can retrieve current approved content.
* FR-05: Administrators shall create, update, publish and archive approved university information.
* FR-06: Knowledge-base entries shall support categories such as admissions, academics, examinations, fees, attendance, departments and campus services.
* FR-07: Published entries shall retain source, category and update information.
* FR-08: Archived or unpublished information shall not be presented as current official information.
* FR-09: The system should support search/retrieval of relevant knowledge-base entries for chatbot queries.

### 5.3 Student Query and Conversation Management
Description and Priority: Student Query and Conversation Management. Priority: High.
Stimulus/Response Sequence: User enters natural-language query → validation → intent classification/retrieval → answer or clarification → conversation continues or escalates.
* FR-10: The chatbot shall accept natural-language questions.
* FR-11: The system shall identify or classify the likely intent/category of a query.
* FR-12: The system shall retrieve relevant approved information for supported questions.
* FR-13: The chatbot shall support relevant follow-up questions within the same conversation.
* FR-14: The system shall provide clarification prompts when a query is ambiguous.
* FR-15: The system should maintain conversation history for authorized users.

### 5.4 AI/NLP Response Generation
Description and Priority: AI/NLP Response Generation. Priority: High.
Stimulus/Response Sequence: Query → intent/context analysis → knowledge retrieval → AI generation → grounding/confidence check → response or escalation.
* FR-16: The AI service shall generate responses using retrieved university context where applicable.
* FR-17: The system shall preserve relevant conversational context for follow-up questions.
* FR-18: Responses shall be concise, understandable and appropriate for university users.
* FR-19: The system shall provide source/reference information where practical for factual university answers.
* FR-20: Unsupported or low-confidence questions shall trigger clarification or human escalation rather than fabricated answers.
* FR-21: AI/service failure shall display an explicit failure state rather than an invented answer.

### 5.5 Academic and Administrative Information
Description and Priority: Academic and Administrative Information. Priority: High.
Stimulus/Response Sequence: User asks service-related question → category identified → approved information retrieved → response displayed.
* FR-22: The system shall support queries about academic procedures, courses and department contacts where such information is available.
* FR-23: The system shall support examination schedules, procedures and FAQs using approved sources.
* FR-24: The system shall support admissions, fee and administrative FAQs using approved sources.
* FR-25: The system shall provide relevant office/contact information for queries requiring direct university assistance.
* FR-26: Personalized university information shall only be shown after appropriate authentication and authorization.

### 5.6 Helpdesk Ticket and Escalation
Description and Priority: Helpdesk Ticket and Escalation. Priority: High.
Stimulus/Response Sequence: Query unresolved/needs action → ticket created → queue/operator assignment → operator response → status update → notification → resolution.
* FR-27: Users shall be able to create a helpdesk ticket from the chatbot when required.
* FR-28: Each ticket shall receive a unique ticket ID.
* FR-29: Tickets shall contain requester, category, description, status, timestamps and relevant conversation context.
* FR-30: Helpdesk operators shall view, respond to and update assigned tickets.
* FR-31: Users shall be able to track ticket status where permitted.
* FR-32: The system shall escalate unresolved or action-requiring requests to the appropriate helpdesk queue.

### 5.7 Notifications and Feedback
Description and Priority: Notifications and Feedback. Priority: Medium.
Stimulus/Response Sequence: Response/ticket event → notification rule → notification delivered → user feedback where applicable.
* FR-33: The system should notify users about ticket creation, operator responses, important status changes and closure.
* FR-34: Users shall be able to rate or provide feedback on chatbot responses.
* FR-35: Feedback shall be associated with the relevant response or conversation.
* FR-36: Administrators shall be able to review aggregated feedback.

### 5.8 Audit and Administration
Description and Priority: Audit and Administration. Priority: High.
Stimulus/Response Sequence: Administrator authenticates → authorization check → management/analytics screen → action → audit record.
* FR-37: Administrators shall manage users, roles and permissions.
* FR-38: Administrators shall manage knowledge-base content, categories and publication status.
* FR-39: The system shall provide analytics such as query volume, common intents, unanswered questions, escalation rate and feedback.
* FR-40: Important authentication, access, ticket, knowledge-base and configuration events shall be auditable.
* FR-41: Administrative functions shall require administrator authorization.

---

## 6. Non-Functional Requirements

### 6.1 Performance
| ID | Requirement | Priority |
|---|---|---|
| NFR-01 | Normal chatbot and navigation interactions should remain responsive for the expected project workload. | High |
| NFR-02 | Knowledge-base retrieval should return relevant results within a configured response target under normal conditions. | Medium |
| NFR-03 | AI generation shall return a result or explicit failure state within a configured service timeout. | High |
| NFR-04 | Long-running AI, search and ticket operations shall show visible processing status. | Medium |
Performance requirements concern response time, processing feedback and efficient use of data. The system should avoid unnecessary data transfer and should provide visible status for AI and ticket operations.

### 6.2 Safety
| ID | Requirement | Priority |
|---|---|---|
| NFR-05 | AI output shall be treated as assistance/information and not as an autonomous university authority. | High |
| NFR-06 | Official policies, deadlines, fees and procedures shall be based on approved sources. | High |
| NFR-07 | Unsupported or low-confidence answers shall be clarified or escalated rather than fabricated. | High |
| NFR-08 | Human helpdesk escalation shall be available for requests requiring institutional action or judgment. | High |

### 6.3 Security and Privacy
| ID | Requirement | Priority |
|---|---|---|
| NFR-09 | Protected functions shall require authentication. | High |
| NFR-10 | Server-side authorization shall be enforced for every protected user, ticket and administrative operation. | High |
| NFR-11 | Sensitive information shall be protected during transmission and storage according to the deployment environment. | High |
| NFR-12 | Significant authentication, access, ticket, content and administrative events shall be auditable. | High |
| NFR-13 | External AI requests should follow data minimization and configured privacy controls. | High |

### 6.4 Usability
The chatbot should use clear language, simple navigation, visible actions and understandable error messages. Common questions should be answerable without unnecessary navigation. Ticket creation and status tracking should be easy for non-technical users.

### 6.5 Reliability
Conversation, ticket and approved knowledge-base records should not be silently lost. If AI, search, notification or ticket processing fails, the system should show an explicit error/fallback state and preserve available user input where practical.

### 6.6 Maintainability
Authentication, chatbot processing, knowledge retrieval, tickets, notifications, administration and audit functions should be organized as modular components/services so they can be independently developed, tested and maintained.

### 6.7 Scalability
The architecture should support growth in users, conversations, knowledge-base entries, tickets and AI requests without requiring a complete redesign.

### 6.8 Traceability and Testability
Every functional and non-functional requirement has a unique identifier. Requirements should be traceable to use cases, DFD/UML models, implementation tasks and test cases. Important chatbot answers should also retain a traceable link to their supporting knowledge-base source where practical.

---

## 7. Business Rules
| Rule ID | Rule | Applicable To |
|---|---|---|
| BR-01 | Students, faculty/staff, helpdesk operators and administrators have different privileges. | All users |
| BR-02 | Protected personal or university account information requires appropriate authentication and authorization. | All users |
| BR-03 | Only authorized administrators may publish or modify official knowledge-base content. | Administrator |
| BR-04 | Archived or unpublished information shall not be presented as current official information. | System |
| BR-05 | AI responses about official university facts should be supported by approved knowledge-base information. | AI/System |
| BR-06 | If supporting information is unavailable or confidence is insufficient, the chatbot shall clarify or escalate rather than invent an answer. | AI/System |
| BR-07 | Tickets requiring human action shall be routed to an appropriate helpdesk queue. | System/Helpdesk |
| BR-08 | Each helpdesk ticket shall have a unique identifier and traceable status history. | System |
| BR-09 | Important authentication, access, content, ticket and administrative events shall be auditable. | System/Admin |
| BR-10 | User feedback should be retained for chatbot-quality analysis. | System |
| BR-11 | Sensitive user information shall not be exposed to unauthorized users or unnecessary external services. | System |
| BR-12 | Academic demonstrations should use synthetic data where real personal data is not required. | Project Team |

---

## 8. Other Requirements
* University-approved information shall be persistently stored in MongoDB or the configured equivalent.
* Knowledge-base records shall retain source, category and update information.
* Conversation and ticket records shall be linked to the relevant user where authentication is available.
* Important ticket status changes and administrative actions should remain traceable.
* Production SSO/ERP/SIS integration, WhatsApp deployment, multilingual expansion and institutional compliance requirements are outside confirmed Version 1.0 unless separately approved.
* Production data retention, backup, disaster recovery and institutional privacy policies shall be finalized before real student personal data is used.

---

## Appendix A: Glossary
| Term | Definition |
|---|---|
| SRS | Software Requirements Specification. |
| DFD | Data Flow Diagram. |
| AI | Artificial Intelligence. |
| NLP | Natural Language Processing. |
| RBAC | Role-Based Access Control. |
| Knowledge Base | Collection of approved university information used to answer supported queries. |
| Intent | The purpose or category inferred from a user's natural-language query. |
| Grounded Response | AI-generated response supported by retrieved approved information. |
| Escalation | Transfer of an unresolved or action-requiring issue to a human helpdesk operator. |
| Ticket | A tracked helpdesk request with an identifier, status and history. |
| Conversation Context | Relevant prior messages used to understand a follow-up query. |
| Audit Log | Record of significant system, access, authentication or administrative events. |

---

## Appendix B: Analysis Models
The analysis-model set for the project includes Use Case, Class, Sequence, Activity, Component, Deployment and State Machine diagrams. The DFD set includes Level 0, Level 1 and Level 2 views covering authentication, query processing, knowledge retrieval, AI response generation, ticket escalation, notifications, feedback and administration.

*(Note: Diagrams are referenced but visual contents such as DFD Level 0, 1, and 2 images are part of the original document)*

---

## Appendix C: To Be Determined List
| TBD ID | Item | Status |
|---|---|---|
| TBD-01 | Production hosting configuration | To be decided during deployment. |
| TBD-02 | Final AI model/provider configuration | To be finalized during implementation. |
| TBD-03 | Final university knowledge-base source/integration | To be finalized with institutional stakeholders. |
| TBD-04 | SSO / university identity integration | Requires institutional technical access and approval. |
| TBD-05 | Production data retention and privacy policy | Requires institutional approval before production use. |
| TBD-06 | Notification provider (email/SMS/push) | To be selected during implementation. |
| TBD-07 | Advanced integrations such as ERP/SIS/WhatsApp | Outside confirmed Version 1.0 unless separately approved. |

---

## Requirement Report Summary
The requirements for the AI Chatbot for University Helpdesk have been organized using the same IEEE style requirement-report structure as the supplied reference. The report includes requirements elicitation, stakeholder identification, prioritization and validation; functional requirements for authentication, knowledge-base management, natural-language query handling, AI response generation, academic and administrative information, ticket escalation, notifications, feedback and administration; and non-functional requirements for performance, safety, security, privacy, usability, reliability, maintainability, scalability, traceability and testability.

The DFD analysis models represent the chatbot as a university helpdesk system connected to users, helpdesk operators and administrators. The core workflow is designed so that approved university information is retrieved before AI response generation, while unsupported or low-confidence requests are clarified or escalated rather than answered with invented institutional information.
