---
sidebar_label: "Update Service"
sidebar_position: 4
---

import gitbookAsset1 from "./update-service.assets/Screenshot from 2025-06-02 14-36-32.png";
import gitbookAsset2 from "./update-service.assets/Screenshot from 2025-06-10 15-19-21.png";
import gitbookAsset3 from "./update-service.assets/Screenshot from 2025-06-02 14-40-45.png";

# Update Service

**Update Service** option is used to update a specific service within the deployment. This applies to the `unity-sh` and `chat-sh` services.

First you need to copy the new jar file to the relevant directory:

1. **Unity-SH:** `/var/ascertia/unityPortal/unityData/`
2. **Chat-SH:** `/var/ascertia/unityPortal/chatData/`

Now follow the steps for the service you wish to update.

**Select the service you wish to update.**

<figure><img src={gitbookAsset1} alt="" /><figcaption></figcaption></figure>

**Select the version to deploy.** Pay close attention to the numbering of the service to ensure you deploy the correct one.

<figure><img src={gitbookAsset2} alt="" /><figcaption></figcaption></figure>

**Deployment.** The service will now be stopped, the new jar file moved to active, the service started and the necessary tools installed and health checks performed.&#x20;

**Once completed the success message will be displayed.**

<figure><img src={gitbookAsset3} alt="" /><figcaption><p>Succes message</p></figcaption></figure>

