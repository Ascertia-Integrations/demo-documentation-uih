---
description: >-
sidebar_label: "Restart Service"
sidebar_position: 4
---

# Restart Service

:::warning
To apply any new environment variable configurations, do not use `sudo docker compose restart <containerName>` as this will not pull in the new values. Always use the below steps:
:::

To restart the Integrations Hub, follow these steps:

Stop existing containers by running:

```bash
sudo docker compose down --remove-orphans
```

:::danger
Wait for the services to stop gracefully. Do not force stop them, as this could damage the encrypted data inside the vault.
:::

Once all the services are indicated as `Removed`, start them back up using the command:

```bash
sudo docker compose up -d
```

:::warning
The containers will be created and start to initialize. Note this can take up to 30 seconds before the system will be able to accept requests.
:::
