---
description: >-
sidebar_label: "View Logs"
sidebar_position: 5
---

# View Logs

There are a few ways to view logs inside Docker. They all start with the base command: `sudo docker compose logs`

* To keep tailing the log, append: `-f`.
* To see the logs for only a specific service, append the service name: `inh_unity-sh`.
* To write the log to a file instead of viewing it on screen, append the appropriate name and optional path: `> /path/to/log/logName.txt`.

Example with all parameters:

```bash
sudo docker compose logs -f inh_unity-sh >> /home/user/Downloads/integrationsHubLog.txt
```

Example with log written to a local path:

```bash
sudo docker compose logs -f inh_unity-sh >> integrationsHubLog.txt
```

