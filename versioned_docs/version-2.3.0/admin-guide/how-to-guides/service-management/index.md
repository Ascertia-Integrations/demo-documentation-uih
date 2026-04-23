---
description: >-
sidebar_label: "Service Management"
sidebar_position: 1
---

# Management

The Unity Integrations Hub is comprised of a set of Docker containers that are orchestrated using Docker Compose. All management tasks for the deployment—such as starting, stopping, updating, or viewing logs for services—can be managed seamlessly using standard `docker compose` commands.

Below are guides for common management operations:

* [Check Status](../../reference/check-status)
  Shows the status of the deployed containers.
* [View Logs](../../reference/view-logs)
  Allows for viewing of all or specific services logs.
* [Stop Service](./stop-service)
  Stops the running services.
* [Restart Service](./restart-service)
  Restart services to apply configuration changes.
* [Update Service](./update-service)
  Used to do an update of a specific service. This typically applies to `unity-sh` and `chat-sh` services.
* [Configure SSL](./configure-ssl)
  Configure secure communication for the portal instance.