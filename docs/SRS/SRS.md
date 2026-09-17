# Software Requirements Specification
for
## AI Chatbot for University Helpdesk
Version 1.0

Prepared by
Aman Gupta - 202401100100035
Abhishek goswami - 202401100100011
Amar Dwivedi - 202401100100036
Abhay Pratap Singh – 202401100100006

KIET Deemed To Be University
Branch: Computer Science (CS) — B.Tech 3rd Year

---

## Revision History
| Version | Date | Author | Reason For Changes |
|---|---|---|---|
| 1.0 | September 2026 | Project Team | Initial SRS for AI Chatbot for University Helpdesk |

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
* 3. External Interface Requirements
  * 3.1 User Interfaces
  * 3.2 Hardware Interfaces
  * 3.3 Software Interfaces
  * 3.4 Communications Interfaces
* 4. System Features
  * 4.1 Authentication and User Management
  * 4.2 University Information and Knowledge Base
  * 4.3 Student Query Handling
  * 4.4 AI/NLP Response Generation
  * 4.5 Academic and Administrative Services
  * 4.6 Escalation and Ticket Management
  * 4.7 Notifications and Feedback
  * 4.8 Analytics and Administration
* 5. Other Nonfunctional Requirements
  * 5.1 Performance Requirements
  * 5.2 Safety Requirements
  * 5.3 Security Requirements
  * 5.4 Software Quality Attributes
  * 5.5 Business Rules
* 6. Other Requirements
* Appendix A: Glossary
* Appendix B: Analysis Models
* Appendix C: To Be Determined List

---

## 1. Introduction

### 1.1 Purpose
This Software Requirements Specification (SRS) defines the functional and non-functional requirements for an AI Chatbot for University Helpdesk. It specifies the system scope, users, conversational workflows, university knowledge-base integration, AI-assisted response generation, escalation, notifications, security expectations, constraints, and acceptance-oriented requirements for Version 1.0.

### 1.2 Document Conventions
This document follows the IEEE-style organization shown in the supplied reference document. Functional requirements use unique FR-xx identifiers. SHALL/MUST indicates a mandatory requirement; SHOULD indicates a recommended requirement.

### 1.3 Intended Audience and Reading Suggestions
The SRS is intended for students, faculty/staff, helpdesk operators, administrators, developers, testers, project guides, and reviewers. Read Sections 1–2 for context, Section 3 for interfaces, Section 4 for detailed features, and Section 5 for non-functional requirements.

### 1.4 Product Scope
The AI Chatbot for University Helpdesk provides a centralized conversational interface through which students and university users can ask questions about admissions, academics, examinations, fees, attendance, departments, campus services, schedules, policies, facilities, and other approved university information. The system retrieves relevant information from an institutional knowledge base and generates concise responses. When the chatbot cannot confidently answer a query or the issue requires human action, it can create or escalate a helpdesk ticket.

### 1.5 References
* IEEE Software Requirements Specification template supplied as the reference document.
* University-approved notices, FAQs, policies, academic calendars and helpdesk documentation.
* AI Chatbot for University Helpdesk UML and Data Flow Diagram (DFD) documentation.
* Project implementation plan and testing documentation.

---

## 2. Overall Description

### 2.1 Product Perspective
The AI Chatbot is a web-based university helpdesk application. The planned architecture uses a React/Vite frontend, Node.js/Express backend, MongoDB for application data, a university knowledge base for approved information, an AI/NLP service for intent detection and response generation, and optional email/SMS/push notification services.

### 2.2 Product Functions
* Student/faculty/staff login and role-based access.
* Natural-language question and answer interface.
* University FAQ and knowledge-base search.
* Intent detection and query classification.
* Context-aware AI response generation using approved university information.
* Answers for admissions, academics, examinations, fees, attendance, departments and campus services.
* Conversation history and suggested follow-up questions.
* Human helpdesk escalation and ticket creation.
* Ticket status tracking and notifications.
* User feedback and response-quality reporting.
* Administrator knowledge-base, user, ticket and analytics management.

### 2.3 User Classes and Characteristics
| User | Main responsibilities |
|---|---|
| Student | Ask university-related questions, view answers, create/track tickets, provide feedback and manage profile. |
| Faculty/Staff | Ask policy/service questions, use approved helpdesk information and submit service requests where permitted. |
| Helpdesk Operator | Review escalated queries, respond to tickets, update ticket status and resolve user issues. |
| Administrator | Manage users, roles, knowledge-base content, categories, chatbot configuration, analytics and audit information. |

### 2.4 Operating Environment
Modern desktop or mobile web browsers; React/Vite frontend; Node.js/Express backend; MongoDB; REST APIs; configured university knowledge-base storage; AI/NLP service; and optional email/SMS/push notification services.

### 2.5 Design and Implementation Constraints
* MERN-oriented implementation.
* Server-side authorization is mandatory for protected operations.
* Only approved and current university information should be used as authoritative chatbot content.
* AI responses should be grounded in retrieved university information where applicable.
* The chatbot SHALL NOT invent official policies, deadlines, fees, examination rules or other institutional facts.
* Sensitive student information shall not be exposed to unauthorized users.
* External AI services may impose availability, rate, cost and data-handling constraints.
* Academic demonstrations should use synthetic/test data where personal data is not required.

### 2.6 User Documentation
The project should provide concise guidance for chatbot usage, login, asking effective questions, ticket creation and tracking, feedback submission, helpdesk operator workflows, and administrator knowledge base management.

### 2.7 Assumptions and Dependencies
* Users have a supported browser and network connection.
* University-approved information is available in a maintained knowledge base.
* MongoDB is available.
* AI/NLP service is available where configured.
* Helpdesk staff are available for escalated requests.
* University policies and FAQs are updated by authorized administrators.

---

## 3. External Interface Requirements

### 3.1 User Interfaces
Student screens include login, chatbot dashboard, conversation history, FAQs/knowledge search, ticket creation, ticket status, notifications and profile. Faculty/staff receive the chatbot and permitted service request screens. Helpdesk operators receive ticket queues, conversation details and response management screens. Administrators receive user/role, knowledge-base, category, chatbot configuration, analytics and audit-management screens.

### 3.2 Hardware Interfaces
No specialized hardware is required for Version 1.0. Standard computers, laptops, tablets and smartphones with a supported browser are sufficient.

### 3.3 Software Interfaces
| Interface | Purpose |
|---|---|
| React/Vite | Web user interface and chatbot conversation experience. |
| Node.js/Express REST API | Business logic, authentication, authorization, conversations and tickets. |
| MongoDB | User, conversation, ticket, feedback and configuration storage. |
| University Knowledge Base | Approved FAQs, notices, policies, schedules and service information. |
| AI/NLP Service | Intent detection, retrieval-assisted response generation and conversational processing. |
| Notification Service | Email/SMS/push notifications for tickets and important updates. |

### 3.4 Communications Interfaces
Frontend-backend communication shall use secure HTTP(S) REST APIs, normally with JSON request/response data. AI, knowledge-base and notification services shall use protected network connections and authenticated requests where supported.

---

## 4. System Features

### 4.1 Authentication and User Management
Description and Priority: Authentication and User Management. Priority: High.
Stimulus/Response Sequence: User selects portal → enters credentials → authentication → permission check → dashboard/chatbot.
* FR-01: The system shall provide secure login for supported university users.
* FR-02: The system shall enforce role-based authorization for student, faculty/staff, helpdesk operator and administrator functions.
* FR-03: Unauthorized requests shall be denied without exposing protected user, ticket or administrative data.
* FR-04: The system should maintain user profile information and session state securely.

### 4.2 University Information and Knowledge Base
Description and Priority: University Information and Knowledge Base. Priority: High.
Stimulus/Response Sequence: Admin publishes/updates content → content is stored/indexed → chatbot retrieves relevant information → answer is generated.
* FR-05: Administrators shall create, update, publish and archive approved university information.
* FR-06: Knowledge-base entries shall support categories such as academics, admissions, examinations, fees, attendance, departments and campus services.
* FR-07: Published content shall retain source, category and update information.
* FR-08: Archived or unpublished information shall not be presented as current official information.

### 4.3 Student Query Handling
Description and Priority: Student Query Handling. Priority: High.
Stimulus/Response Sequence: User enters query → query validation → intent detection/retrieval → response generation → answer displayed.
* FR-09: The chatbot shall accept natural-language questions.
* FR-10: The system shall identify or classify the likely intent/category of a user query.
* FR-11: The system shall retrieve relevant approved information for supported university queries.
* FR-12: The system shall display the answer with relevant source information where practical.
* FR-13: The chatbot shall support follow-up questions within a conversation.
* FR-14: Unsupported or ambiguous questions shall trigger clarification or escalation rather than fabricated answers.

### 4.4 AI/NLP Response Generation
Description and Priority: AI/NLP Response Generation. Priority: High.
Stimulus/Response Sequence: Query → intent/context analysis → knowledge retrieval → AI generation → confidence/grounding check → response or escalation.
* FR-15: The AI service shall generate responses using the retrieved university context where applicable.
* FR-16: The system shall preserve conversation context for relevant follow-up questions.
* FR-17: Responses shall be concise, understandable and appropriate for university users.
* FR-18: The chatbot shall avoid inventing official facts when supporting information is unavailable.
* FR-19: Low-confidence, unsupported or policy-sensitive queries shall be routed to clarification or human helpdesk.
* FR-20: AI/service failure shall show an explicit failure state rather than fabricated content.

### 4.5 Academic and Administrative Services
Description and Priority: Academic and Administrative Services. Priority: High.
Stimulus/Response Sequence: User asks service-related question → category identified → approved information retrieved → response shown.
* FR-21: The system shall support queries related to academic procedures, course information and department contacts where such data is available.
* FR-22: The system shall support examination-related FAQs, schedules and procedures using approved sources.
* FR-23: The system shall support admissions, fees and administrative FAQs using approved sources.
* FR-24: The system shall provide relevant office/contact information for queries requiring direct university assistance.
* FR-25: Personalized data shall only be shown after appropriate authentication and authorization.

### 4.6 Escalation and Ticket Management
Description and Priority: Escalation and Ticket Management. Priority: High.
Stimulus/Response Sequence: Query unresolved/needs action → create ticket → assign queue/operator → operator response → status update → user notification.
* FR-26: Users shall be able to create a helpdesk ticket from the chatbot when required.
* FR-27: The system shall assign a unique ticket ID.
* FR-28: Tickets shall contain category, description, requester, status, timestamps and relevant conversation context.
* FR-29: Helpdesk operators shall view, respond to and update assigned tickets.
* FR-30: Users shall be able to track ticket status where permitted.
* FR-31: The system shall notify users when important ticket status changes occur.

### 4.7 Notifications and Feedback
Description and Priority: Notifications and Feedback. Priority: Medium.
Stimulus/Response Sequence: Response/ticket event → notification rule → notification delivered → user feedback where applicable.
* FR-32: The system should notify users about ticket creation, assignment, responses and closure.
* FR-33: Users shall be able to rate or provide feedback on chatbot responses.
* FR-34: Feedback shall be associated with the relevant response or conversation.
* FR-35: Administrators shall be able to review aggregated feedback.

### 4.8 Analytics and Administration
Description and Priority: Analytics and Administration. Priority: High.
Stimulus/Response Sequence: Admin authenticates → permission checked → analytics/configuration displayed.
* FR-36: Administrators shall manage users, roles and permissions.
* FR-37: Administrators shall manage knowledge-base content and categories.
* FR-38: The system shall provide analytics such as query volume, common intents, unanswered queries, escalation rate and feedback.
* FR-39: Administrative actions and significant authentication, ticket and configuration events shall be auditable.
* FR-40: Administrative functions shall require administrator authorization.

---

## 5. Other Nonfunctional Requirements

### 5.1 Performance Requirements
* Normal navigation and chatbot interaction should remain responsive for the expected project workload.
* Knowledge-base retrieval should return results within a configured response target under normal conditions.
* Long-running AI, search or ticket operations shall show processing states.
* AI generation shall return a result or explicit failure state within a configured timeout.
* The system should avoid sending unnecessary personal information to external AI services.

### 5.2 Safety Requirements
* The chatbot is an information and helpdesk assistant, not an autonomous authority for university policy.
* Official policies, deadlines, fees and procedures should be based on approved sources.
* Conflicting or outdated information shall be flagged or routed for administrator review.
* AI failure or low-confidence responses must not be replaced with invented information.
* Human escalation shall be available for queries requiring institutional action or judgment.

### 5.3 Security Requirements
* Authentication is required for protected functions.
* Server-side authorization shall protect every protected user, ticket and administrative operation.
* Sensitive student information shall only be visible to authorized users.
* Sensitive data shall be protected in transit and at rest according to deployment.
* Important access, authentication, ticket, knowledge-base and administrative events shall be auditable.
* External AI/service requests shall follow configured data-minimization and security controls.

### 5.4 Software Quality Attributes
| Attribute | Requirement |
|---|---|
| Usability | Simple conversational workflow with clear answers and minimal unnecessary navigation. |
| Reliability | Conversations, tickets and approved knowledge-base records should not be silently lost. |
| Maintainability | Authentication, chatbot, knowledge base, tickets, notifications and analytics should be modular. |
| Traceability | Responses should retain links or references to relevant approved information where practical. |
| Security | Protected user and administrative data is accessible only to authorized users. |
| Testability | Requirements should be verifiable through unit, API, integration, AI-evaluation and UI tests. |
| Scalability | Architecture should support growth in users, conversations, knowledge-base entries and tickets. |

### 5.5 Business Rules
* Students, faculty/staff, helpdesk operators and administrators have different privileges.
* Only authorized administrators may publish official knowledge-base information.
* Personalized university information requires appropriate authentication.
* AI responses must not be treated as official when no approved supporting information exists.
* Queries requiring human action should be escalated to the appropriate helpdesk queue.
* Ticket IDs and status history should remain traceable throughout the support workflow.

---

## 6. Other Requirements
* University-approved information shall be persistently stored in MongoDB or the configured equivalent.
* Knowledge-base content shall retain source and update information.
* Conversation and ticket records shall be linked to the relevant user where authentication is available.
* Academic demonstrations should use synthetic/test user data where real personal data is not required.
* Production institutional integrations, SSO, ERP/SIS integration, WhatsApp/SMS deployment, multilingual support and compliance requirements are outside confirmed Version 1.0 unless separately approved.

---

## Appendix A: Glossary
| Term | Meaning |
|---|---|
| SRS | Software Requirements Specification. |
| DFD | Data Flow Diagram. |
| AI | Artificial Intelligence. |
| NLP | Natural Language Processing. |
| RBAC | Role-Based Access Control. |
| Knowledge Base | Collection of approved university information used to answer supported queries. |
| Intent | The purpose or category inferred from a user's query. |
| Escalation | Transfer of an unresolved or action-requiring issue to a human helpdesk operator. |
| Ticket | A tracked helpdesk request with an identifier, status and history. |
| Grounded Response | AI-generated response supported by retrieved approved information. |

---

## Appendix B: Analysis Models
The AI Chatbot analysis-model set includes Use Case, Class, Sequence, Activity, Component, Deployment and State Machine diagrams. The project DFD includes Level 0, Level 1 and Level 2 views covering authentication, query processing, knowledge-base retrieval, AI response generation, ticket escalation, notifications and administration.

*(Note: Diagrams are referenced but visual contents such as DFD Level 0, 1, and 2 images are part of the original document)*

---

## Appendix C: To Be Determined List
| TBD ID | Item | Status |
|---|---|---|
| TBD-01 | Production hosting configuration | To be decided during deployment. |
| TBD-02 | Final AI model/provider configuration | To be finalized during implementation. |
| TBD-03 | Final university knowledge-base source/integration | To be finalized with institutional stakeholders. |
| TBD-04 | SSO / university identity integration | Requires institutional approval and technical access. |
| TBD-05 | Production data retention and privacy policy | Requires institutional approval before production use. |
| TBD-06 | Notification provider (email/SMS/push) | To be selected during implementation. |

---

## Requirement Summary
The AI Chatbot for University Helpdesk shall provide a secure conversational helpdesk platform for university users. It shall authenticate users where required, answer supported questions using approved university information, maintain relevant conversation context, provide source-aware and understandable responses, and avoid fabricating official institutional facts. It shall support human escalation through tracked helpdesk tickets, notifications and feedback. The system shall enforce role-based access control, protect sensitive information, maintain auditability for important operations, and provide administrative tools for knowledge-base and chatbot management.

The supplied reference SRS uses an IEEE-style structure with dedicated sections for introduction, overall description, interfaces, system features, non-functional requirements, glossary, analysis models and a TBD list; this document follows that same organizational approach while adapting the requirements to the university-helpdesk chatbot topic.
