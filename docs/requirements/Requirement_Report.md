# 1. Title Page
**Project Title**: AI-Powered University Helpdesk Chatbot
**Document Type**: Requirement Report
**Project Type**: Academic Software Engineering Project
**Date**: September 10, 2026

---

# 2. Document Information
**Document Name**: Requirement_Report.md
**Version**: 1.0
**Description**: High-level requirements and scope for the AI-Powered University Helpdesk Chatbot system.

---

# 3. Project Overview
The "AI-Powered University Helpdesk Chatbot" is an intelligent software system designed to assist university students by providing immediate, accurate answers to university-related inquiries using natural language processing (NLP). The chatbot serves as a centralized knowledge access point for campus policies, academic schedules, administrative processes, and general student queries.

---

# 4. Background
Universities typically handle a massive volume of student inquiries regarding admissions, examinations, schedules, and administrative policies. Students often face difficulties finding accurate and timely information, as they must navigate complex university websites or wait for responses from administrative staff during business hours. 

---

# 5. Problem Statement
Currently, students struggle with slow response times from university helpdesks and face difficulty locating scattered information across various department portals. This manual query resolution process is inefficient, causing frustration for students and adding unnecessary workload to the university's administrative staff, particularly during peak periods like admissions and examinations.

---

# 6. Proposed Solution
The proposed solution is an AI-powered conversational agent that students can interact with using natural language. The chatbot will be backed by a university-specific knowledge base, allowing it to retrieve relevant information dynamically and answer common queries instantly, 24/7. Administrators will be provided with a simplified interface to maintain the knowledge base, ensuring information remains up to date.

---

# 7. Project Objectives
- To develop a chatbot capable of understanding and answering student queries using natural language.
- To centralize scattered university information into a single, manageable knowledge base.
- To reduce the administrative burden on university staff by automating responses to frequent inquiries.
- To provide a user-friendly interface for administrators to update the knowledge base.
- To implement graceful fallback mechanisms when the chatbot cannot confidently answer a question.

---

# 8. Project Scope
**In-Scope:**
- Natural language querying by students on topics such as Admissions, Courses, Exams, Fees, Hostels, Library, etc.
- Administrator capabilities to add, edit, and delete knowledge base documents.
- Basic conversation history tracking for the student.
- Fallback response generation when the chatbot cannot find an answer.
- Basic dashboard/analytics for administrators to view usage.

**Out-of-Scope:**
- Integration with external live student databases (e.g., retrieving a specific student's personal grades, as this adds complex security requirements beyond the scope of this project).
- Live chat handoff to human agents.
- Voice/Speech recognition capabilities.

---

# 9. Stakeholders
- **Students**: Primary end-users interacting with the chatbot for information.
- **System Administrators / University Staff**: Users responsible for updating and maintaining the chatbot's knowledge base.
- **Project Evaluation Committee / Faculty**: Academic evaluators assessing the software engineering project.

---

# 10. Stakeholder Requirements

| ID | Requirement | Description | Priority |
| :--- | :--- | :--- | :--- |
| SR-01 | 24/7 Information Access | Students require access to university information outside of standard working hours. | Must Have |
| SR-02 | Accurate Responses | Stakeholders require the system to provide correct information based exclusively on the university knowledge base. | Must Have |
| SR-03 | Easy Content Management | Administrators require a straightforward interface to update knowledge without coding knowledge. | Must Have |
| SR-04 | System Feedback Loop | Students should be able to provide simple feedback on whether a response was helpful. | Should Have |
| SR-05 | Usage Visibility | Administrators should be able to see basic metrics (e.g., total queries, common topics) to understand student needs. | Could Have |

---

# 11. User Requirements
**Student Requirements:**
- The student must be able to ask questions in plain English.
- The student must receive an answer within a few seconds.
- The student must be notified gracefully if the chatbot does not know the answer.

**Administrator Requirements:**
- The administrator must be able to securely log into the system.
- The administrator must be able to upload or type text-based information into the knowledge base.
- The administrator must be able to remove outdated policies from the system.

---

# 12. Functional Requirements

| ID | Requirement | Description | Priority |
| :--- | :--- | :--- | :--- |
| FR-01 | Submit Query | The system shall allow a Student to input a natural language text query. | Must Have |
| FR-02 | Generate Response | The system shall generate a text response to the Student's query based on the knowledge base. | Must Have |
| FR-03 | Conversation Context | The system shall maintain context within a single active conversation session. | Should Have |
| FR-04 | Conversation History | The system shall allow Students to view their past conversation history. | Could Have |
| FR-05 | Fallback Handling | The system shall provide a standard fallback message directing the user to a human contact if an answer cannot be found. | Must Have |
| FR-06 | Admin Authentication | The system shall require Administrators to log in with a username and password. | Must Have |
| FR-07 | Knowledge Base Addition | The system shall allow Administrators to add new information blocks to the knowledge base. | Must Have |
| FR-08 | Knowledge Base Modification | The system shall allow Administrators to edit or delete existing information blocks. | Must Have |
| FR-09 | Submit Feedback | The system shall allow Students to rate a chatbot response (e.g., helpful/not helpful). | Should Have |
| FR-10 | View Basic Metrics | The system shall display basic usage statistics (total chats, popular topics) to Administrators. | Could Have |

---

# 13. Non-Functional Requirements

| ID | Requirement | Description | Priority |
| :--- | :--- | :--- | :--- |
| NFR-01 | Performance (Response Time) | The chatbot shall return a response to a query within 5 seconds under normal load. | Must Have |
| NFR-02 | Usability | The student chat interface shall be intuitive and require no training to use. | Must Have |
| NFR-03 | Maintainability | The system's codebase shall be well-documented and modular to allow for easy updates by future students. | Must Have |
| NFR-04 | Security (Admin) | Administrator passwords must be hashed and not stored in plaintext. | Must Have |
| NFR-05 | Privacy | The system shall not request or store highly sensitive personal student information (e.g., SSN, passwords) in the chat logs. | Must Have |
| NFR-06 | Scalability | The system should be able to handle up to 50 concurrent student users without severe degradation in response time. | Should Have |
| NFR-07 | Availability | The system should aim for 99% uptime during the academic evaluation period. | Should Have |

---

# 14. Hardware Requirements
- **Server/Hosting Environment**: Standard cloud instance (e.g., 2vCPUs, 4GB RAM) or equivalent local machine for development and presentation.
- **Client**: Any device (PC, laptop, smartphone) with an internet connection and a modern web browser.

---

# 15. Software Requirements
- **Operating System (Server)**: Linux/Windows.
- **Client**: Modern web browsers (Chrome, Firefox, Safari, Edge).
- **Backend/Frontend Frameworks**: To be decided in the design phase (e.g., Python, Node.js, React, HTML/CSS).
- **Database**: To be decided (e.g., PostgreSQL, MongoDB, SQLite) for storing chat logs and knowledge base texts.
- **AI/NLP Engine**: Any suitable NLP or Large Language Model API (to be decided during implementation).

---

# 16. System Constraints
- **Budget**: As an academic project, the system must utilize free-tier cloud services, open-source databases, and affordable or free AI APIs.
- **Time**: The project must be completed within the current academic semester.
- **AI Limitations**: The AI is not guaranteed to be 100% accurate and may occasionally "hallucinate," hence the strict requirement for it to rely solely on the provided knowledge base.

---

# 17. Assumptions and Dependencies
- **Assumptions**: 
  - Students will query the chatbot in English.
  - The university will provide initial sample data (dummy data for the project) to populate the knowledge base.
- **Dependencies**: 
  - The system relies on the availability and uptime of the chosen AI/NLP API or library.
  - The system requires a stable internet connection on the client side.

---

# 18. Business Rules
- Only authorized users with "Administrator" roles can modify the knowledge base.
- The chatbot must not provide specific academic advice (e.g., "Which elective should I take?") but only objective facts (e.g., "What electives are offered?").
- If the knowledge base contains conflicting information, the most recently updated entry takes precedence.

---

# 19. Requirement Prioritization
The requirements in Sections 10, 12, and 13 follow the MoSCoW method:
- **Must Have**: Core functionality required for the academic project submission (e.g., querying, answering, admin updates, fallback).
- **Should Have**: Important features that add significant value but are not strictly critical (e.g., feedback, context).
- **Could Have**: "Nice-to-have" features if time permits (e.g., usage metrics, chat history).

---

# 20. Requirement Traceability Overview
*(A complete traceability matrix will be maintained in later phases. Below is a high-level overview.)*
- **SR-01 (24/7 Access)** maps to **FR-01, FR-02, NFR-07**.
- **SR-02 (Accurate Responses)** maps to **FR-05, FR-07, FR-08, NFR-05**.
- **SR-03 (Content Management)** maps to **FR-06, FR-07, FR-08**.

---

# 21. Risks and Mitigation

| Risk | Impact | Mitigation Strategy |
| :--- | :--- | :--- |
| **AI Hallucinations** | High | Strictly prompt/constrain the AI to only use retrieved knowledge base facts. Implement robust fallback handling (FR-05). |
| **API Rate Limits/Costs** | Medium | Use free-tier services wisely during development; implement request caching if necessary. |
| **Scope Creep** | Medium | Strictly adhere to the "Out-of-Scope" list; avoid integrating live student databases. |
| **Data Loss** | Low | Regularly backup the database; rely on dummy data for the academic presentation. |

---

# 22. Future Scope
- Integration with the university's student information system to answer personalized queries (e.g., "What is my GPA?").
- Multilingual support for international students.
- Integration into popular messaging platforms (e.g., WhatsApp, Discord, or Microsoft Teams).
- Voice interaction capabilities.

---

# 23. Acceptance Criteria
The project will be considered successful if:
1. A user can type a question regarding university policies and receive a relevant answer sourced from the knowledge base.
2. The chatbot responds with a polite fallback message when asked a question unrelated to the university or outside its knowledge base.
3. An administrator can successfully log in, add a new piece of information, and the chatbot can immediately answer questions about that new information.
4. The system operates stably during the academic demonstration without crashing.

---

# 24. Conclusion
This Requirement Report outlines the foundational needs, functional capabilities, and constraints for the AI-Powered University Helpdesk Chatbot. By adhering strictly to these requirements and focusing on the core knowledge-base retrieval features, the development team will deliver a robust, academic-level software engineering project that effectively addresses the problem of student information accessibility.
