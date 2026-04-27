---
icon: hand-wave
sidebar_label: "Welcome"
sidebar_position: 1
slug: "/"
---

import gitbookAsset1 from "./index.assets/Slide3.png";

# Welcome

The **Unity Integrations Hub** is a backend component, that enables a new generation of integrations. The Hub offloads a lot of the responsibilities common to the different integrations, into a single place.&#x20;

:::info
The **Unity Integrations Hub** sits between SigningHub and the final integration (e.g. SharePoint), acting as a middle layer coordinating the information exchange between both services.
:::

### Who is this guide for?

**This guide is for system administrators with deep software deployment knowledge.**&#x20;

The documentation will guide you through the deployment of a backend component that will act as a coordinator for business applications (integrations) deployed on other platforms (as SharePoint and Microsoft Teams).

:::info
For Ascertia SaaS users as SigningHub.com, the Unity Integrations Hub is already deployed and managed by Ascertia.
:::

### Key Features

* **RESTful Endpoints.** Standardised API endpoints for easy consumption.
* **Authentication.** Secure access using OAuth 2.0.
* **Data Management.** Retrieve, update, and manage data efficiently.
* **Scalability.** Optimised for high-performance integrations.

This API serves as the backbone for third party application integrations, enabling them to interact with SigningHub in a structured and reliable manner.

### Why the Unity Integrations Hub?

The **Unity Integrations Hub** makes the integrations smaller while providing the same functionality. As integrations are smaller, and the complexity lies on the **UIH,** enables: faster development of new integrations, better maintainability, and improvements on QA, among others.

<figure><img src={gitbookAsset1} alt="" width="375" /><figcaption></figcaption></figure>

> _Being a server side middle layer, final users won't have to interact orknow of the existence of the Unity Integrations Hub. **It is transparent for the final user.**_

Is designed to provide secure and efficient endpoints for integrating third party applications with SigningHub. This API facilitates seamless data exchange, authentication, and process automation, ensuring interoperability with SigningHub.
