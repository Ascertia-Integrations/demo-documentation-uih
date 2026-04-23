---
description: >-
sidebar_label: "Integrations Hub Installation"
sidebar_position: 1
---

# Integrations Hub Installation

:::tip
Ensure the Docker repository is configured on the system before proceeding. The installer package will automatically install docker and docker-compose as dependencies. [See Docker Pre-requisites for details.](../docker-installation-upgrade)
:::

**Make sure the latest installer is available;** it is a file named: `int-hub_[version].deb`

The installer packages two core components: the Integrations Hub and the Chat SigningHub modules.

:::info
**What does this installer actually do?** Unlike traditional installers that map raw application files into the host operating system, this `.deb` package installs Docker container images. It extracts pre-packaged Hub services so they can be run in secure, isolated virtual environments rather than directly on the host server.
:::

Installer versioning is composed of three elements: the installer version itself, the packaged Integrations Hub version, and the packaged Chat SigningHub version.

`int-hub_<installerVersion>_inh<integrationsHubVersion>_chat<chatVersion>.deb`  where:

* `<installerVersion>` is X.Y.Z.
* `<integrationsHubVersion>` is X.Y.Z.
* `<chatVersion>` is X.Y.Z.

The final file name will look like this example: \
`int-hub_2.3.0_inh2.3.0_chat2.0.5.deb`

:::info
Versions might have attached a build number in case of pre-release versions of the different modules, following the pattern `2.X.X_XXXXXXXXXXXXX` .
:::

### Deployment Steps

Copy the installation file to the Ubuntu user's downloads folder. **Start the install using `apt`:**&#x20;

```bash
sudo apt install -f ./int-hub_[version].deb
```

The installation will then begin. The installer will execute the below steps:

* Automatically install Docker and Docker-compose dependencies (if not already present).
* Set directory permissions and change to `/opt/ascertia/int-hub`.
* Load and install the required docker images.
* Run the environment setup, including generating new configuration files.
* Set up the configuration by generating the environment and OAuth tokens.
* Update the active JAR references in the environment file.

Once successfully completed, the below message will be displayed:

```text
══════════════════════════════════════════════════════════════════
 INSTALLATION SUCCESSFUL
══════════════════════════════════════════════════════════════════
Please see user guide for steps to start/stop/manage the 
Integrations Hub instance: 
https://docs.ascertia.com/unity-integrations-hub/
```

:::info
**Note:** The last warning about “Permission denied” is expected in a restricted environment. This does not affect usability of the system.
:::

Once installed, move to the Integrations Hub directory:

```
cd /opt/ascertia/int-hub/
```

Start the services that make up the Integrations Hub with Docker:

```
sudo docker compose up 
```

The logs will show the following services starting up:

* `inh_apache`: Use to serve static web resources.
* `inh_vault`: Used as secure/encrypted storage for sensitive information.
* `inh_unity-sh`: The core unity service that processes workflows.
* `inh_chat-sh`: The extension of unity that bridges chat platforms to unity.
* `inh_nginx`: Central proxy into the environment that provides load balancing and SSL.

The `d` key can now be pressed to detach from docker logging.
