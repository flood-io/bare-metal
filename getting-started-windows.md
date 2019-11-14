---
description: >-
  This quick start guide will show you how to run Flood Agent on Windows using
  your own machine.
---

# Getting Started \(Windows\)

## Download and Install

The guide shows you how to run ad-hoc instances, suitable for exploration & prototyping floods. For production-scale installations see [Running with NSSM \(Windows\)](deployment/running-with-nssm-windows.md).

## Download

{% hint style="info" %}
_Please note:_ until the first official release please grab the latest _pre-release_ from the [GitHub Releases page](https://github.com/flood-io/flood-agent/releases/)
{% endhint %}

We recommend downloading the agent into its own directory. For the guide, let's assume you've chosen to use `c:\flood-agent`:

![](.gitbook/assets/flood-agent-windows-install%20%281%29.png)

## Flood API Token

Grab your Flood API token from [https://app.flood.io/account/user/security](https://app.flood.io/account/user/security)

![Flood Security Settings Page](.gitbook/assets/flood-access-token.png)

## Configure the agent

The simplest method for creating a configuration file is the guided `flood-agent.exe configure` wizard.

Otherwise, create a configuration file yourself at `c:\flood-agent\config.yaml`  with the following contents:

{% tabs %}
{% tab title="config.yaml" %}
```yaml
flood_api_token: flood_live_f100d1e9a8e # as grabbed above
tools:
  jmeter:
    jmeter_home: C:\Path\To\JMeter
```
{% endtab %}
{% endtabs %}

{% hint style="warning" %}
If your `jmeter_home` path contains a space, make sure you escape it with a backslash `\` before each space.
{% endhint %}

{% hint style="warning" %}
Support for running load generators as Docker containers on Windows is under development but is not yet available.
{% endhint %}

## Check your configuration

Next, check the configuration:

```text
.\flood-agent.exe check

~# Flood Agent #~ : configuration checker
[>] config read from c:\flood-agent\config.yaml

==> Checking Flood API
[√] api token - ok

==> Checking tools
[√] jmeter - ok
[ ] no gatling config
[ ] no flood-element config

==> Checking network
[√] AWS S3 Archives endpoint - connectivity ok
[√] Flood configuration service - connectivity ok
[√] Flood data pipeline ingress - connectivity ok
[√] Flood status service - connectivity ok
[√] AWS sns endpoint in us-east-1 - connectivity ok
[√] AWS sqs endpoint in us-east-1 - connectivity ok
```

If you're running `flood-agent` from within a corporate network, you may need to perform additional steps to get started. For more information, please see the [Networking](deployment/networking.md) page.

## Run the agent

In a console, run

```text
cd c:\flood-agent
flood-agent.exe --grid windowsgrid1
```

Your agent will start, outputting some informational logging. The agent is organised into the flood grid `windowsgrid1`

{% hint style="success" %}
If you perform the above on a second machine, your grid `windowsgrid1` will now have two nodes. Any floods scheduled onto `windowsgrid1` will now run on both machines.
{% endhint %}

For more information on how it works, please see [How it works](how-it-works.md).

## Run a flood

Visit https://app.flood.io and create a flood as normal \(or _Start more like this_\)

![](.gitbook/assets/test-step-1.png)

progress through the steps until Step 6, where you'll choose `windowsgrid1` .

![](.gitbook/assets/image%20%281%29.png)

Launch the test.

### Shutting down

Your Flood Agent instance will check in every few seconds to notify Flood that it is alive. If you stop the process or disconnect from the internet/close your laptop, it will be removed from Flood after 1 minute. 

You can reconnect it at any time.

