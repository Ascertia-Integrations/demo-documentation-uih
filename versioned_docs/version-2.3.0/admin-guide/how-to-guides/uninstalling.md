---
description: >-
sidebar_label: "Uninstalling"
sidebar_position: 4
---

# Uninstalling

To uninstall the package, first stop and clear the deployed instance. Note that this only removes the package, not the stored data:

```bash
sudo docker compose down --remove-orphans
```

Next, remove the installer from the package manager:

```bash
sudo apt remove int-hub -y
```

:::danger
Proceeding below will clear the stored data. Be aware that this removes the encrypted vault and any customized data since the installation. This task cannot be undone; it will be as if the hub was never installed.
:::

To completely remove anything remaining, use the command:

```bash
sudo rm -rf /opt/ascertia/int-hub
```
