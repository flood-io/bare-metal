---
description: >-
  Setting up Flood Agent to communicate through a web proxy for outbound web
  access to the Flood platform.
---

# Integrating with a web proxy

There are numerous instances where usage of a web proxy is mandatory in corporate environments. Flood Agent supports the use of the operating system level environment variables called `http_proxy` and `https_proxy`.

**Linux, OS X, or Unix**

```text
export HTTP_PROXY=http://[user]:[pass]@[proxy_ip]:[proxy_port]/
export HTTPS_PROXY=http://[user]:[pass]@[proxy_ip]:[proxy_port]/
```

**Windows**

```text
setx http_proxy=http://[user]:[pass]@[proxy_ip]:[proxy_port]/
setx https_proxy=http://[user]:[pass]@[proxy_ip]:[proxy_port]/
```

Once this has been set - you can simply run the Flood Agent and it should adhere to the new `http_proxy` settings.

