---
description: Start using Flood Agent with Docker based load generators
---

# Getting Started - Docker

If your system has Docker installed, using Flood's pretuned Docker images is the simplest way to start using Flood Agent.

{% hint style="warning" %}
Running load generators via Docker is not currently supported on Windows. To use Flood Agent on windows, please see [Getting Started - Local JMeter & Gatling](getting-started-local-jmeter-and-gatling.md).
{% endhint %}

## Copy your Flood API token

The first step is to copy your Flood API token from the Flood dashboard.

1. Click here to visit the [Flood API Access page](https://app.flood.io/account/user/security).
2. Click on _Reveal token_ under _Flood IO API v2.0._ You should see something like this:

![](.gitbook/assets/flood-access-token.png)

3. Copy the string beginning with flood\_live to your clipboard; you'll need it in the next step.

## Run the agent

Run the `flood-agent` binary that you downloaded in the previous section of the Getting Started guide. Use the token that you copied in the previous step:

{% tabs %}
{% tab title="Linux & Mac" %}
```text
./flood-agent --token flood_live_f100d1e9a8e...
```
{% endtab %}

{% tab title="windows" %}
```
.\flood-agent.exe --token flood_live_f100d1e9a8e...
```
{% endtab %}
{% endtabs %}

Flood Agent will use a random grid name like `submerged-dolphin`.

You can also specify a custom name for your grid. For example, `mygrid`

{% tabs %}
{% tab title="Linux & Mac" %}
```text
./flood-agent --token flood_live_f100d1e9a8e... --grid mygrid1
```
{% endtab %}

{% tab title="windows" %}
```
.\flood-agent.exe --token flood_live_f100d1e9a8e... --grid mygrid1
```
{% endtab %}
{% endtabs %}

{% hint style="success" %}
If you repeat these steps on a second machine, your grid `mygrid1` will now have two nodes. Any floods you run on `mygrid1` will now run on both machines.

For more information, please see [How it Works](how-it-works.md).
{% endhint %}

## Verify the agent

Once the agent has started you should start seeing some informational logging:

```text
~# Flood Agent #~
==> Contacting Flood API...
--> checking Flood API token
[√] token valid
--> syncing with API as mygrid1
[√] sync done
==> Bootstrapping Flood agent...
[2s] ~ starting Flood Agent ~ version: dev build: dev
[5s] Using stdout-only logs
[5s][mygrid1] 
[5s][mygrid1] load generator config summary
[5s][mygrid1] java-selenium-firefox:
[5s][mygrid1]   as docker container
[5s][mygrid1] jmeter:
[5s][mygrid1]   as docker container
[5s][mygrid1] gatling:
[5s][mygrid1]   as docker container
[5s][mygrid1] floodchrome:
[5s][mygrid1]   as docker container
[5s][mygrid1] floodelement:
[5s][mygrid1]   as docker container
[5s][mygrid1] java-selenium-chrome:
[5s][mygrid1]   as docker container
[5s][mygrid1] 
[8s][mygrid1][agent] ready, awaiting Flood jobs
[8s][mygrid1][job-worker] awaiting next job
```

If you're still having trouble starting `flood-agent`, try the `flood-agent check‌` command. For more details see the ["Check your Configuration" section on the Getting Started - Local JMeter & Gatling page](getting-started-local-jmeter-and-gatling.md#check-your-configuration).

If you're running flood-agent from within a corporate network, you may need to perform additional steps to get started. For more information, please see the [Networking page.](deployment/networking.md)

## Next, run a load test

To continue to launch a load test, check out [Running a flood on your grid](running-a-flood-on-your-grid.md).



