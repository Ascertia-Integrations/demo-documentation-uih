---
description: Follow this section when deploying the UIH behind a reverse proxy.
sidebar_label: "Reverse Proxy Configuration for UIH with CORS Support"
sidebar_position: 3
---

# Reverse Proxy Configuration for UIH with CORS Support

This section contains considerations when deploying the Integrations Hub behind a reverse proxy. 

:::info
**What are we configuring here?** 
A **Reverse Proxy** acts as a middleman that manages internet traffic before it hits the internal Hub. **CORS** (Cross-Origin Resource Sharing) is a security feature that stops malicious sites from making unauthorized browser requests. 

We must configure the reverse proxy to explicitly attach CORS headers that tell client browsers: _"Yes, requests connecting to this Hub are authorized."_
:::

Because the Integrations Hub operates as a Docker stack composed of specialized services, an improperly configured reverse proxy can cause system issues by dropping essential request headers.

The following Nginx configuration is provided as a demonstration of which headers must be forwarded for the system to function correctly.

## Nginx Example Configuration

Demonstration Nginx Reverse Proxy Configuration for UIH with CORS Support. Demo values are designated as follows:

* Using the `demo` keyword in paths and settings.
* Using `0.0.0.0` for placeholder IP addresses.

```nginx
# Demonstration Nginx Reverse Proxy Configuration for UIH with CORS Support
# Demo values designated with 'demo' in paths and settings, and 0.0.0.0 IPs
 
server {
  listen       80;
  listen       443 ssl;
  server_name  demo.com;
  ignore_invalid_headers on;
  underscores_in_headers on;
  
  # SSL configuration
  ssl_prefer_server_ciphers off;
  ssl_protocols TLSv1.2;
  ssl_ciphers DEMO-DEMO-DEMO-DEMO-DEMO-DEMO-DEMO-DEMO-DEMO;
  ssl_session_cache shared:WEB:10m;
  ssl_certificate /etc/nginx/sslcerts/demo.pem;
  ssl_certificate_key /etc/nginx/sslcerts/demo.key;
  ssl_session_timeout 1d;
  ssl_session_tickets on;
  ssl_dhparam /etc/nginx/conf.d/dhparam;
  
  client_max_body_size 250M;
  
  access_log  /var/log/nginx/access.log adv;
  error_log  /var/log/nginx/error.log info;
 
  # Below determines the headers passed to the UIH backend services
  ### UNITY PATH SETTINGS ###################################################
  location /unity-sh/ {
    proxy_pass https://0.0.0.0;
    proxy_set_header Host $host;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-Proto $scheme;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_set_header Forwarded "for=$remote_addr;proto=$scheme";
 
    # Add CORS (Cross-Origin Resource Sharing) headers to allow requests from any origin
    proxy_hide_header Access-Control-Allow-Origin;
    add_header 'Access-Control-Allow-Origin' '*' always;
    proxy_hide_header Access-Control-Allow-Methods;
    add_header 'Access-Control-Allow-Methods' 'GET, POST, OPTIONS, PUT, DELETE' always;
    proxy_hide_header Access-Control-Allow-Headers;
    add_header 'Access-Control-Allow-Headers' 'Origin, Content-Type, Accept, Authorization' always;
    proxy_hide_header Access-Control-Allow-Credentials;
    add_header 'Access-Control-Allow-Credentials' 'true' always;
 
    # Handle preflight requests for CORS
    if ($request_method = OPTIONS ) {
    add_header 'Access-Control-Allow-Origin' '*' always;
    add_header 'Access-Control-Allow-Methods' 'GET, POST, OPTIONS, PUT, DELETE' always;
    add_header 'Access-Control-Allow-Headers' 'Origin, Content-Type, Accept, Authorization' always;
    add_header 'Access-Control-Allow-Credentials' 'true' always;
      return 204;
    }
  }
 
    ### CHAT-SH PATH SETTINGS ###################################################
  location /chat-sh/ {
    proxy_pass https://0.0.0.0;
    proxy_set_header Host $host;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-Proto $scheme;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_set_header Forwarded "for=$remote_addr;proto=$scheme";
 
    # Add CORS (Cross-Origin Resource Sharing) headers to allow requests from any origin
    proxy_hide_header Access-Control-Allow-Origin;
    add_header 'Access-Control-Allow-Origin' '*' always;
    proxy_hide_header Access-Control-Allow-Methods;
    add_header 'Access-Control-Allow-Methods' 'GET, POST, OPTIONS, PUT, DELETE' always;
    proxy_hide_header Access-Control-Allow-Headers;
    add_header 'Access-Control-Allow-Headers' 'Origin, Content-Type, Accept, Authorization' always;
    proxy_hide_header Access-Control-Allow-Credentials;
    add_header 'Access-Control-Allow-Credentials' 'true' always;
 
    # Handle preflight requests for CORS
    if ($request_method = OPTIONS ) {
      add_header 'Access-Control-Allow-Origin' '*' always;
      add_header 'Access-Control-Allow-Methods' 'GET, POST, OPTIONS, PUT, DELETE' always;
      add_header 'Access-Control-Allow-Headers' 'Origin, Content-Type, Accept, Authorization' always;
      add_header 'Access-Control-Allow-Credentials' 'true' always;
      return 204;
    }
  }
 
  ### APACHE PATH SETTINGS ##################################################
  location /apache/ {
    proxy_pass https://0.0.0.0;
    proxy_set_header Host $host;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_set_header X-Forwarded-Proto $scheme;
 
    proxy_hide_header Access-Control-Allow-Origin;
    add_header 'Access-Control-Allow-Origin' '*' always;
    proxy_hide_header Access-Control-Allow-Methods;
    add_header 'Access-Control-Allow-Methods' 'GET, POST, OPTIONS, PUT, DELETE' always;
    proxy_hide_header Access-Control-Allow-Headers;
    add_header 'Access-Control-Allow-Headers' 'Origin, Content-Type, Accept, Authorization' always;
    proxy_hide_header Access-Control-Allow-Credentials;
    add_header 'Access-Control-Allow-Credentials' 'true' always;
  }
 
  ### BLOCKED PATHS #########################################################
  location /vault {
    return 403;
  }
 
  ### BASE PATH #############################################################
  location / {
    return 200 "Hello From UnityPortal - Nginx";
  }
}
```
