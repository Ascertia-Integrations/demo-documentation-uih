---
description: >-
icon: square-terminal
sidebar_label: "Management"
sidebar_position: 1
---

import gitbookAsset1 from "./index.assets/Screenshot from 2025-06-02 14-02-13.png";

# Management

The unity-service script provides basic management functionality for the Unity Integrations Hub.&#x20;

1. **Deploy New Environment**\
   Deploys a new environment, this can be Development, QA/Testing, Staging  and Production.
2. **Deploy Previous Environment**\
   Deploys the same environment that was previous deployed and stopped.
3. **Update Service**\
   Used to do an update of a specific service. This applies to unity-sh and chat-sh services.
4. **Restart Services**\
   This is for use when a change was made to the docker-compose config and the service(s) needs to be restarted to apply the change
5. **View Logs**\
   Allows for viewing of all or specific services logs.
6. **Check Status**\
   Shows the status of the deployed containers
7. **Stop All**\
   Stops all the running services.

<figure><img src={gitbookAsset1} alt="" /><figcaption></figcaption></figure>

> The options might change order between different versions
