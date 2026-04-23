---
description: Docker and Docker Compose installation guide
sidebar_label: "Docker Installation/Upgrade"
sidebar_position: 2
---

# Docker Pre-requisites (Ubuntu 22.04)

The **Unity Integrations Hub** installation uses `apt` to automatically fetch and install **docker** and **docker-compose-plugin** as dependencies. 

To ensure that the installer pulls the latest versions of Docker straight from the official Docker repositories (instead of the older Ubuntu default repositories), configure the Docker official GPG key and repository on the system before proceeding.

### Stop Old Instance

:::warning
If any old instance of UIH is actively running. Stop that first before continuing with the new v2.2.x installation.
:::

### Set Up Docker Repository

Open a terminal and update the System:&#x20;

```bash
sudo apt update && sudo apt upgrade
```

Remove any old (docker core v1) version if installed:&#x20;

```bash
sudo apt remove docker docker-engine docker.io containerd runc
```

Install the Docker dependencies:&#x20;

```bash
sudo apt install ca-certificates curl gnupg lsb-release
```

Set permissions

```bash
sudo install -m 0755 -d /etc/apt/keyrings
```

Add the Docker's GPG Key:

```bash
sudo mkdir -p /etc/apt/keyrings curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

Set Up the Repository&#x20;

```bash
echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
$(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

Update the Package Lists Again:&#x20;

```bash
sudo apt update
```

Docker is now ready to be automatically installed as a dependency by the Integrations Hub installer package. Please continue with the Integrations Hub deployment.
