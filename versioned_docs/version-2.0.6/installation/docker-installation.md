---
description: Docker and Docker Compose installation guide
hidden: true
sidebar_label: "Docker installation"
sidebar_position: 3
---

# Docker installation

The following describes installing **docker** and **docker-compose** on **Ubuntu 22.04**, use the appropriate steps for your specific installation.

### Docker Installation

Open a terminal and update the System:&#x20;

```bash
sudo apt update && sudo apt upgrade
```

Remove any old version if installed:&#x20;

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

Update  the Package Lists Again:&#x20;

```bash
sudo apt update
```

Install Docker:&#x20;

```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

Verify Installation:&#x20;

```bash
sudo docker run hello-world
```

### Docker Compose Installation

:::warning
Run the following commands after installing Docker, one after the other, do not close the session before completing all the steps outlined below.
:::

Update the software repository

```bash
sudo apt-get update
```

Install Docker Compose:

```bash
sudo apt-get install docker-compose-plugin
```

Verify version:

```bash
docker compose version
```
