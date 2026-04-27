---
description: Static resources specific for each integration
icon: upload
sidebar_label: "Deploying Static Resources on Apache"
sidebar_position: 5
---

import gitbookAsset1 from "./deploying-static-resources-on-apache.assets/image (14).png";

# Deploying Static Resources on Apache

Static resources are used by the different integrations connected to the given **Unity Integrations Hub** each integration might use this files for different purposes.

:::info
Default data might be deployed with the Unity Integrations Hub installer, that you can override according to the documentation for each integration.
:::

### Static files

The static files will be under the `static` folder alongside the integration package, or provided separately in case the integration is installed from an application repository (e.g., Sharepoint Store).

:::tip
**If you have not received these files, you can skip this section,** they are not needed for the integration and/or version you are using.
:::

### Install the static files

Login to your docker server and browse to `/var/ascertia/unityPortal/apacheData/apache`, this is the root directory of the web server.&#x20;

You can deploy any additional resources here or in subfolders, as mandated by the given integration documentation.

:::info
Usually integrations will use a sub-folder with the name of the integration (e.g., `sharepoint/)`
:::

> **Example**
>
> If provided with the static file: `static/sample-image.png` , it should be copied into the apache folder:  `.../apache/sharepoint/sample-image.png` ).

<figure><img src={gitbookAsset1} alt="" width="563" /><figcaption></figcaption></figure>

### Verify the installation

To access resources, you can use the following URL inside the deployment machine: `http://apache/index.html` to see the served assets.
