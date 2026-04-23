---
description: >-
sidebar_label: "What is Deployed"
sidebar_position: 4
---

# What is Deployed

The installer deploys the **Unity Integrations Hub** in the directory: `/opt/ascertia/int-hub` .

<figure><img src="/img/gitbook/image (19).png" alt="" /><figcaption></figcaption></figure>

:::info
**Understanding the Folder Structure:** Each folder maps directly to a specific containerized service within the Hub as a "volume," ensuring data persists even if the Docker containers restart. For example, `unityData/` powers the central authentication and document-routing module, while `chatData/` specifically bridges message-based platforms (like Microsoft Teams) into that flow.
:::

* **`apacheData/`**: Stores all files served by the internal Apache service.
* **`backups/`**: Directory used to back up the Vault's active cryptographic configuration, user settings, and customer profiles when upgrading an existing deployment.
* **`chatData/`**: Storage space for the `chat-sh` service. This contains both historical release versions and the active executable, `ShChat.jar`.
* **`docker-compose.yml`**: The active Docker Compose configuration file orchestrating the container ecosystem.
* **`License.txt`**: Contains product licensing information.
* **`int-hub.sh`**: A bash script that provides general management functionality for the portal and its underlying services.
* **`nginxData/`**: Stores custom configurations for the Nginx reverse proxy.
* **`nginxData/ssl/`**: The standard location for SSL certificates utilized by Nginx.
* **`templates/`**: Holds configuration templates, particularly for `docker-compose` and environment variable defaults.
* **`unityData/`**: Storage space for the core `unity-sh` service. It houses the active `UnityPortal.jar` executable alongside previous versions.
* **`vaultData/`**: Persistent storage for the HashiCorp Vault. It safely stores encrypted user and customer settings, as well as initialization scripts and Vault logs.
