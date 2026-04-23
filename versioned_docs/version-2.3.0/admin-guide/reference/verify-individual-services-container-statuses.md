---
description: >-
sidebar_label: "Verify Individual Services/Container Statuses"
sidebar_position: 3
---

# Verify Individual Services/Container Statuses

To verify the different services, check the following:

### Vault

The vault should have successfully started and unsealed. Run the command:

```bash
sudo docker compose logs inh_vault
```

Ensure the `Sealed` status is shown as `false`.

### Unity-sh

Look at the unity logs by running the command:

```bash
sudo docker compose logs inh_unity-sh
```

Ensure the following message is displayed:
`inh_unity-sh | [2026-02-10 10:41:50] [INFO] [UnityPortalApplication] Started UnityPortalApplication in 3.638 seconds (process running for 4.053)`

Check the service status by accessing the below URL in a browser, replacing `server.domain.com` with the server name. The IP address can also be used:
`http://server.domain.com/unity-sh/status/about`

A message starting with the following should be displayed:
`Services running`

### Chat-sh

Get the log file by running the command:

```bash
sudo docker compose logs inh_chat-sh
```

Look for a message showing its uptime is displayed:
`inh_chat-sh | [2026-02-10 10:41:54] [INFO] [ShChatApp] Started ShChatApp in 2.231 seconds (process running for 2.718)`

Check the service status by opening the below URL in a browser. Replace `server.domain.com` with the server name. The IP address can also be used:
`https://server.domain.com/chat-sh/v1/status`

Its uptime should be displayed along with other information:
`"uptime": "0 days, 0 hours, 35 minutes, 39 seconds"`

### Apache

Check the log file by running the command:

```bash
sudo docker compose logs inh_apache
```

Look for a line indicating normal operations are running:
`inh_apache | [Tue Feb 10 10:41:40.663575 2026] [mpm_event:notice] [pid 1:tid 1] AH00489: Apache/2.4.66 (Unix) configured -- resuming normal operations`

Check the service status by opening the below URL in a browser. Replace `server.domain.com` with the server name. The IP address can also be used:
`https://server.domain.com/apache/index.html`

This message should be displayed:
`Welcome to Unity Portal - Apache Service`

### Nginx

Check the log file by running the command:

```bash
sudo docker compose logs inh_nginx
```

Look for a line indicating normal operations are running:
`inh_nginx | 2026/02/10 10:41:52 [notice] 1#1: start worker processes`

Check the service status by opening the below URL in a browser. Replace `server.domain.com` with the server name. The IP address can also be used:
`https://server.domain.com/index.html`

This message should be displayed:
`Hello From UnityPortal - Nginx`

## Successful Installation

With everything up and running, the integrations can start connecting to the Unity Integrations Hub.

:::tip
Follow each of the individual integrations documentation for instructions on how to connect to the Unity Integrations Hub deployment.
:::
