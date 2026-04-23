---
description: >-
sidebar_label: "Upgrading"
sidebar_position: 2
---

# Upgrading

To upgrade an existing installation of the Integrations Hub to a newer version, simply download the latest `.deb` installer and run it using `apt`, just like a [new installation](./). The installer will automatically handle migrating configurations, updating active JAR references, and creating backups of existing components within the `backups/` directory.

```bash
sudo apt install -f ./int-hub_[version].deb
```
