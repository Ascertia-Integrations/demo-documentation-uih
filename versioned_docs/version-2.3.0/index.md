---
description: >-
icon: house
sidebar_label: "Welcome"
sidebar_position: 1
slug: "/"
---

# Welcome

The **Integrations Hub,** previously named Unity Integrations Hub, is a backend component that enables a new generation of integrations. The Hub offloads a lot of the responsibilities common to the different integrations into a single place.&#x20;

:::info
The **Integrations Hub** sits between SigningHub and the final integration (e.g. SharePoint), acting as a middle layer coordinating the information exchange between both services.
:::



### Key Features

* **RESTful Endpoints.** Standardised API endpoints for easy consumption.
* **Authentication.** Secure access using OAuth 2.0.
* **Data Management.** Retrieve, update, and manage data efficiently.
* **Scalability.** Optimised for high-performance integrations.

This API serves as the backbone for third party application integrations, enabling them to interact with SigningHub in a structured and reliable manner.

### Why the Integrations Hub?

The **Integrations Hub** makes the integrations smaller while providing the same functionality. As integrations are smaller, and the complexity lies on the **IH**, it enables faster development of new integrations, better maintainability, and improvements on QA, among others.

<figure><img src="/img/gitbook/Slide3.png" alt="Diagram showing the Integration Hub acting as a middle layer between SigningHub and a third-party application." width="375" /><figcaption></figcaption></figure>

> _Being a server side middle layer, final users won't have to interact or know of the existence of the Unity Integrations Hub. **It is transparent for the final user.**_

It is designed to provide secure and efficient endpoints for integrating third party applications with SigningHub. This API facilitates seamless data exchange, authentication, and process automation, ensuring interoperability with SigningHub.

## Documentation Sections

[admin-guide](admin-guide/)
