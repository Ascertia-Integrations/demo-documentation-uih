---
description: Static resources specific for each integration
hidden: true
sidebar_label: "Deploying Static Resources on Apache"
sidebar_position: 4
---

import gitbookAsset1 from "./deploying-static-resources-on-apache.assets/image (11).png";

# Deploying Static Resources on Apache

Static resources are used by the different integrations connected to the given **Unity Integrations Hub**. Each integration might use these files for different purposes.

:::info
Default data might be deployed with the Unity Integrations Hub installer, which can be overridden according to the documentation for each integration.
:::

### Static files

The static files will be under the `static` folder alongside the integration package, or provided separately in case the integration is installed from an application repository (e.g., Sharepoint Store).

:::tip
**If these files have not been provided, this section can be skipped,** as they are not needed for the integration and/or version being used.
:::

### Install the Static Files

Login to the docker server and browse to `/opt/ascertia/int-hub/apacheData/apache`, which is the root directory of the web server.&#x20;

Any additional resources can be deployed here or in subfolders, as mandated by the given integration documentation.

:::info
Usually integrations will use a sub-folder with the name of the integration (e.g., `sharepoint/`).
:::

> **Example**
>
> If provided with the static file: `static/sample-image.png` , it should be copied into the apache folder:  `.../apache/sharepoint/sample-image.png`.

<figure><img src={gitbookAsset1} alt="" width="563" /><figcaption></figcaption></figure>

### Verify the Installation

To access resources, the following URL can be used inside the docker host machine: `http://localhost/apache/index.html` to see the served assets.