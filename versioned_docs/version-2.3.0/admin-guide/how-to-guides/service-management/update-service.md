---
description: >-
sidebar_label: "Update Service"
sidebar_position: 3
---

# Update Service

The active JAR files used by the `unity-sh` and `chat-sh` services can be updated.

First, copy the new JAR file to the relevant directory:
* **Unity-SH:** `/opt/ascertia/int-hub/unityData/`
* **Chat-SH:** `/opt/ascertia/int-hub/chatData/`

Update the relevant line in the environment file using the command `sudo vim .env` to specify the new file name. For example:
* **Unity-SH:** `UNITY_ACTIVE_JAR=UnityPortal-2.2.0.jar`
* **Chat-SH:** `CHAT_ACTIVE_JAR=ShChat-2.0.5.jar`

Save the changes by pressing `Esc`, then type `:wq` and press `Enter`.

In order for the changes to take effect, restart the Integrations Hub. Please refer to the [Restart Service](./restart-service) guide.
