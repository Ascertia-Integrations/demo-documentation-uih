---
description: >-
sidebar_label: "Requirements"
sidebar_position: 2
---

# Requirements

The Portal requires the following for successful deployment:

### Minimum Hardware Requirements

* 2 CPU Cores, x64
* 8 GiB Memory
* 2 GiB Hard drive space

### Software

* Ubuntu 22.04\
  `lsb_release -a`
* Docker v25.0.0+\
  `docker version --format '{{.Server.Version}}'`
* Docker Compose v2.20.0+\
  `docker compose version`

### Configuration

* **Ports.** The host docker server must expose ports to the internet.
  * 80
  * 443
