---
description: >-
icon: broom-wide
sidebar_label: "Uninstalling"
sidebar_position: 6
---

import gitbookAsset1 from "./uninstalling.assets/image (20).png";

# Uninstalling

### **Uninstalling the Unity Integrations Hub**

**To uninstall the Unity Integrations Hub,** Login to the docker host server and open a terminal.

Browse to the portal folder: `/var/ascertia/unityPortal`

:::danger
**Warning.** These steps are destructive and cannot be undone.
:::

Start the unity service and stop any running deployments by pressing `[6]`, then selecting `[y]`.

<figure><img src={gitbookAsset1} alt="" /><figcaption></figcaption></figure>

Once stopped, you can exit the menu, **the Unity Integrations Hub has been removed from the machine.**

### Removing remaining configuration files

Now run the following command to uninstall the package:

```
sudo apt remove --purge unity-portal
```

**(Optional)** Some config files are kept in place, to ensure they are removed as well, run this command:

```
sudo rm -rf /var/ascertia/unityPortal
```

**The Unity Integrations Hub has now been removed.**
