---
description: >-
sidebar_label: "Configure SSL"
sidebar_position: 2
---

# Configure SSL

Ensure port 443 is open to the docker host to allow external access.

Ensure a DNS record is assigned to the DNS name that matches the one in the certificate and points to the server's static IP address.

Ensure the SSL certificates are available, with exact names and no password protection as below:
* The private SSL certificate: `ssl.key`
* The public key with full chain: `ssl.crt`

Copy the `ssl.key` and `ssl.crt` files to the folder: `/opt/ascertia/int-hub/nginxData/ssl/`

Now edit the environment file:
```bash
cd /opt/ascertia/int-hub/
sudo vim .env
```

Under the Nginx section, set SSL to enabled:
```env
NGINX_USE_SSL=true
```

Specify the full domain name as it is in the certificate:
```env
NGINX_SERVER_NAME=cert.server.name.com
```

Save and quit by pressing `Esc`, then type `:wq` and press `Enter`.

Restart the service and its containers. First stop them:
```bash
sudo docker compose down --remove-orphans
```

Then start them:
```bash
sudo docker compose up -d
```

Access to the service should now be available using SSL. Replace `cert.server.name.com` in the below URL and open it in a browser:
```text
https://cert.server.name.com/apache/index.html
```
