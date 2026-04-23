---
sidebar_label: "UIH - Verify Installation"
sidebar_position: 5
---

# UIH - Verify Installation

To verify the different services. Check the following:

### Vault

The successful unsealing of the vault should be logged

<figure><img src="/img/gitbook/Screenshot from 2025-06-10 12-47-09.png" alt="" /><figcaption></figcaption></figure>

### Unity-sh

Ensure the application was successfully started after which the CheckVaultStatus calls should start to execute

<figure><img src="/img/gitbook/Screenshot from 2025-06-10 12-39-57.png" alt="" /><figcaption></figcaption></figure>

Check the service status on the URL: [http://--serverName--/unity-sh/status/about](http://dockerhost/unity-sh/status/about)\
You should see the message "Services running"

<figure><img src="/img/gitbook/Screenshot from 2025-06-10 12-53-13.png" alt="" /><figcaption></figcaption></figure>

### Chat-sh

Check for successful service startup

<figure><img src="/img/gitbook/Screenshot from 2025-06-10 12-41-40.png" alt="" /><figcaption></figcaption></figure>

If the service is running, you should be able to load the URL [http://--serverName--/chat-sh/v1/status](http://dockerhost/chat-sh/v1/status) that wil indicate the uptime and other relevant performance data:

<figure><img src="/img/gitbook/Screenshot from 2025-06-10 12-55-15.png" alt="" /><figcaption></figcaption></figure>

### Apache

Check that the service resumed normal operation, after which the /apache/index.html page should be called by the health check

<figure><img src="/img/gitbook/Screenshot from 2025-06-10 12-42-55.png" alt="" /><figcaption></figcaption></figure>

Access the URL  [http://--serverName--/apache/index.html](http://dockerhost/apache/index.html) and ensure it loads

<figure><img src="/img/gitbook/Screenshot from 2025-06-10 14-41-27.png" alt="" /><figcaption></figcaption></figure>

### Nginx

Check that the worker processes is started and that the / path is being called by the health check

<figure><img src="/img/gitbook/Screenshot from 2025-06-10 12-44-44.png" alt="" /><figcaption></figcaption></figure>

Now check the URL [http://--serverName--/index.html](http://dockerhost/index.html) and ensure it loads correctly

<div align="left"><figure><img src="/img/gitbook/Screenshot from 2025-06-10 14-46-10.png" alt="" /><figcaption></figcaption></figure></div>

## Successful Installation

With everything up and running, the integrations can start connecting to the Unity Integrations Hub.&#x20;

:::tip
Follow each of the individual integrations documentation for instructions on how to connect to your Unity Integrations Hub deployment.&#x20;
:::
