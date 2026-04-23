---
sidebar_label: "Deploy New Environment"
sidebar_position: 2
---

# Deploy New Environment

Deploys and setup a new environment using the templates under the `./config` folder.

**Environment to deploy.** First you will need to select the environment you desire to deploy. Once selected you'll have access to different options based on the environment and current setup.

<figure><img src="/img/gitbook/Screenshot from 2025-06-02 14-12-18 (2).png" alt="" /><figcaption></figcaption></figure>

### **1. \[Optional] SSL Configuration**

**Configure SSL:** The user will be presented with the option to configure SSL. If declined, the system will only enable port 80 through Nginx. If accepted, the system will start the process to setup SSL and its certificates.&#x20;

:::warning
**Important** the certificates must be at hand in order to complete this setup.
:::

First specify the full DNS name for the server. This must match the one specified within the SSL certificates

<figure><img src="/img/gitbook/Screenshot from 2025-06-04 12-06-18.png" alt="" /><figcaption></figcaption></figure>

Using a different terminal, copy the certificates to the path and names:\
`Public: /var/ascertia/unityPortal/nginxData/ssl/ssl.crt`\
`Private: /var/ascertia/unityPortal/nginxData/ssl/ssl.key`

:::warning
**Note:** The path and names must match exactly.
:::

<figure><img src="/img/gitbook/Screenshot from 2025-06-04 12-08-19.png" alt="" /><figcaption></figcaption></figure>

The SSL configs will then be updated and the rest of the preparation process continue.

### 2. \[If Re-Deploying] Deploying an Already Existing Environment

In case a previous deployment was already done, the system will warn the user about this.&#x20;

:::danger
Note that replacing a previous environment will render any associated configurations, user or customer level, for that environment unusable.&#x20;

If you do choose to override it, a backup will be placed in the "./backups" folder should there be a need to retrieve it later.
:::

<figure><img src="/img/gitbook/Screenshot from 2025-06-02 14-14-38.png" alt="" /><figcaption></figcaption></figure>

### Common Deployment Steps

**Stop all services.** To continue deploying a new environment, all previous started services must first be stoped. Confirm and continue.

<figure><img src="/img/gitbook/Screenshot from 2025-06-02 14-18-13 (3).png" alt="" /><figcaption></figcaption></figure>

Next the the user can select the version of the UIH service they want to deploy. &#x20;

<figure><img src="/img/gitbook/Screenshot from 2025-06-02 14-21-00.png" alt="" /><figcaption></figcaption></figure>

Now you can select the version of the chat service you want to deploy

<figure><img src="/img/gitbook/Screenshot from 2025-06-02 14-26-21.png" alt="" /><figcaption></figcaption></figure>

Various steps will now be completed to start up the containers and install needed tools. The user can monitor these steps and once complete the success message will be displayed:

<figure><img src="/img/gitbook/Screenshot from 2025-06-02 14-31-38.png" alt="" /><figcaption></figcaption></figure>

The message `UnityPortal successfully deployed`  marks the process as completed.
