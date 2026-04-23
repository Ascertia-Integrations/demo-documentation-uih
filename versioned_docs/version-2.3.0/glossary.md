---
description: >-
icon: book
sidebar_label: "Glossary of Terms"
sidebar_position: 2
---

# Glossary of Terms

To ensure this documentation is accessible to all technical backgrounds, this glossary defines the essential systems, tools, and acronyms referenced throughout the Integrations Hub guides.

### Ascertia Ecosystem
* **SigningHub:** Ascertia's core digital signature and document approval engine.
* **Integrations Hub (UIH):** The main product covered in these docs. It's a backend middleware that coordinates interactions between external business applications (like SharePoint or Teams) and the core SigningHub platform.

### Architecture & Networking
* **Nginx:** A high-performance web server that the Hub uses as a **Reverse Proxy**. 
* **Reverse Proxy:** A server that sits in front of backend applications and forwards client (e.g., browser) requests to those applications. It helps increase security, performance, and reliability by handling SSL decryption and load balancing before traffic hits the vulnerable internal network.
* **CORS (Cross-Origin Resource Sharing):** A browser security feature restricting web pages from making requests to a different domain than the one that served the web page. The Integrations Hub reverse proxy must be configured to allow specific external domains.

### Containerization
* **Docker:** A platform that uses OS-level virtualization to deliver software in packages called **containers**. Containers isolate software from its environment and ensure that it works uniformly despite differences for instance between development and staging.
* **Docker Compose:** A tool for defining and running multi-container Docker applications. The Hub uses Compose files to link its various services together using a single command.

### Security
* **HashiCorp Vault:** An identity-based secrets and encryption management system. The Hub uses it to securely store, access, and deploy sensitive data like cryptographic keys, API tokens, and passwords without hardcoding them into configuration files.
* **OAuth 2.0:** The industry-standard protocol for authorization. It allows external applications to securely act on behalf of a user in SigningHub by issuing access tokens rather than sharing user credentials.
