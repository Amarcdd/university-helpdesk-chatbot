# Deployment Diagram

## 1. Diagram Title
**AI-Powered University Helpdesk Chatbot - Logical Deployment Diagram**

## 2. Purpose
This diagram shows a technology-neutral deployment architecture representing the physical or logical hardware nodes that host the software components. It satisfies the Operating Environment requirements defined in the SRS without locking into a specific vendor.

## 3. Nodes Involved
- Student Device
- Administrator Device
- Web/Application Server
- AI/NLP Processing Service (External or Internal API)
- Knowledge Base Storage (Database Node)

## 4. UML Diagram

```mermaid
flowchart TD
    %% Client Nodes
    subgraph ClientNetwork [Client Networks]
        StudentNode(<<"Device Node">>\n Student PC / Smartphone)
        AdminNode(<<"Device Node">>\n Administrator PC)
    end

    %% Server Nodes
    subgraph CloudEnvironment [Hosting Environment]
        WebServer(<<"Server Node">>\n Web / Application Server)
        DBNode(<<"Database Node">>\n Knowledge Base Storage)
    end
    
    %% External Nodes
    subgraph ExternalServices [External Services]
        AIApi(<<"Service Node">>\n AI/NLP Processing Service)
    end

    %% Network Connections
    StudentNode -- "HTTPS / WebSockets" --> WebServer
    AdminNode -- "HTTPS" --> WebServer
    
    WebServer -- "Internal Network (TCP/IP)" --> DBNode
    WebServer -- "HTTPS / REST API" --> AIApi

```

## 5. Short Explanation
The deployment model consists of client devices (used by students and administrators) communicating securely over the internet via HTTPS to the central `Web / Application Server`. The application server hosts the backend logic and communicates internally with the `Knowledge Base Storage` node. When natural language generation is required, the application server securely interfaces with an abstract `AI/NLP Processing Service`, fulfilling the system's operational environment constraints while remaining cloud-agnostic.
