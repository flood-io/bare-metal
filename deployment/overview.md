# Overview

Flood Agent is distributed as a single binary and only needs a couple of pieces of information to run. This makes integrating it into your infrastructure very easy.

In these guides we suggest a couple of common approaches.

We suggest glancing at [How it works](../how-it-works.md) for an explanation of how Grids integrate with Flood services.

### Flood token

The Flood Agent authenticates with your Flood account using an API token which can be retrieved from the following area when you are logged in to the Flood web application.

![Using the API Access menu link with the Flood application - you are able to get the API token.](../.gitbook/assets/image%20%284%29.png)

Simply copy/paste the API token shown as follows:

![](../.gitbook/assets/image%20%285%29.png)

This API token `flood_live_1234xxxxxx` will need to be added to your local `config.yaml` file in order for the Flood Agent to communicate successfully.

### Grid name

Every Grid using the Flood Agent will be assigned a new name automatically upon startup. If you would like to include multiple nodes within the same Grid then you are able to specify the Grid name to use on each node by supplying the following line within your `config.yaml` file.

```text
grid_name: myGrid1
```

