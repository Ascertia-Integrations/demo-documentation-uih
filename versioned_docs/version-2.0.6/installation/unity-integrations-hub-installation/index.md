---
sidebar_label: "Unity Integrations Hub installation"
sidebar_position: 1
---

import gitbookAsset1 from "./index.assets/Screenshot from 2025-06-02 12-34-40.png";
import gitbookAsset2 from "./index.assets/Screenshot from 2025-06-04 11-57-15.png";

# Unity Integrations Hub installation

:::tip
Ensure docker and docker-compose is installed and ready to use. [See Docker installation steps on how to install docker compose.](../docker-installation)
:::

**Make sure you have the installer,** it is a file named: `unity-portal_X.Y.Z_A.deb`  where `X.Y.Z_A` denote the version of the Unity Integrations Hub the installer will deploy (e.g., `2.0.5_24` ).

### Deployment Steps

Copy the installation file to your Ubuntu user's your downloads folder.

And install using `apt`:&#x20;

```
sudo apt install ./unity-portal_2.0.5_24.deb
```

<figure><img src={gitbookAsset1} alt="UIH installer successful execution" /><figcaption></figcaption></figure>

:::info
**Note:** The last warning about “Permission denied” is expected in a restricted environment. This does not affect usability of the system:
:::

### What is deployed

The installer deploys the **Unity Integrations Hub** in the directory: `/var/ascertia/unityPortal` .

<figure><img src={gitbookAsset2} alt="" /><figcaption></figcaption></figure>

* **active\_environment:** this is the bookmark for the currently active environment.
* **apacheData:** This is where all the files served by the apache service is stored.
* **backups:** This directory is used to create backups of the active crypto config for the vault and the user and customer settings it stores when a new deployment is done over an existing one.
* **chatData:** This is the storage space for the `chat-sh service`. It contains current released versions as well as the active one named `ShChat.jar`.
* **config:** Used to store templates and config files. Specifically for `docker-compse` and vault.
* **docker-compose.yml:** This is the active docker-compose config.
* **License.txt:** Licensing information
* **nginxData:** Used to store nginx specific templates and configs
* **nginxData>ssl:** Location for the SSL certificates used by nginx.
* **unityData:** The storage space for the unity-sh service. It contains the active jar (`UnityPortal.jar`)  as well as other released versions.
* **unity-service:** Bash script that provides management functionality of the portal and its services.
* **vaultData:** Storage space for the `HashiCorp` Vault that stores user and customer settings in encrypted form as well as the initialisation script and logs.

