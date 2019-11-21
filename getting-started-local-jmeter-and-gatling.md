---
description: Start using Flood Agent with locally installed load generators
---

# Getting Started - Local JMeter & Gatling

Flood Agent can use a local installation of JMeter or Gatling to run load tests with [Flood](https://flood.io).

To use one of these local installations you need to:

* create a configuration file for Flood Agent to find the location of the local installation
* ensure that the local installation contains the required Flood reporting plugin.

## Preparing the load generator

To allow load metrics to be collected by the Flood data ingestion pipeline, an existing load generator installation requires a Flood reporting plugin to be added.

Alternatively, we provide distributions of JMeter and Gatling, both prebundled with the plugin. 

For more information, see the specific instructions:

* [JMeter](configuration-1/jmeter.md)
* [Gatling](configuration-1/gatling.md)

## Create the configuration file

The simplest method of configuring Flood Agent is to execute the command `flood-agent configure`. This will start the wizard, which will ask you questions about your API token and the tools you'd like to use for this agent. At the end, it will ask you if you want it to write the config file for you. Select yes.

‌ If you prefer, you can skip the configuration wizard and create the configuration file yourself at `~/flood-agent/config.yaml` . The file should have the following contents:

```text
flood_api_token: flood_live_f100d1e9a8e # as grabbed above
tools:
  jmeter:
    jmeter_home: /path/to/jmeter_home
```

## Check your configuration

Next, check the configuration using the command `flood-agent check` . You should see something like this:

```text
~# Flood Agent #~ : configuration checker
[>] config read from /home/user/flood-agent/config.yaml
​
==> Checking Flood API
[√] api token - ok
​
==> Checking tools
[√] jmeter - ok
[ ] no gatling config
[ ] no flood-element config
​
Next, check the configuration using the command ./flood-agent check . You should see something like this:
​
==> Checking network
[√] AWS S3 Archives endpoint - connectivity ok
[√] Flood configuration service - connectivity ok
[√] Flood data pipeline ingress - connectivity ok
[√] Flood status service - connectivity ok
[√] AWS sns endpoint in us-east-1 - connectivity ok
[√] AWS sqs endpoint in us-east-1 - connectivity ok
```

If you're running `flood-agent` from within a corporate network, you may need to perform additional steps to get started. For more information, please see the [Networking](deployment/networking.md) page.

## Next, run a load test

To continue to launch a load test, check out [Running a flood on your grid](running-a-flood-on-your-grid.md).

