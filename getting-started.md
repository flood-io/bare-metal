---
description: Follow these steps to start using Flood Agent on Linux
---

# Getting Started on Linux

In this guide we'll get Flood Agent running on your Linux computer.

The guide shows you how to run ad-hoc instances, suitable for exploration & prototyping floods. For production-scale installations see [Running with systemd \(linux\)](deployment/running-with-systemd-linux.md).

## Download

Grab the latest binary from the [Flood Agent Releases page](https://github.com/flood-io/flood-agent/releases/latest). We recommend downloading the agent into its own directory. Once the binary has been downloaded, make it executable.

Download: [flood-agent v1.0 64bit for linux](https://github.com/flood-io/flood-agent/releases/download/v1.0/flood-agent-v1.0-linux-64bit)

Here are the steps above as you might use them via the terminal:

```text
mkdir -p ~/flood-agent
cd ~/flood-agent
curl -L https://github.com/flood-io/flood-agent/releases/download/v1.0/flood-agent-v1.0-linux-64bit \
    > flood-agent
chmod +x ./flood-agent
```

{% hint style="success" %}
In the terminal, to run a binary from the current directory, don't forget the `./`

For example, to run Flood Agent: `./flood-agent`
{% endhint %}

## Decide how to run your load generator

From here you need to decide whether you want to run your load generator as a Docker container, or from a local installation of JMeter or Gatling.

* To use flood's load generator docker images see [Getting Started - Docker](getting-started-docker.md)
* To use a locally JMeter or Gatling installation see [Getting Started - Local JMeter & Gatling](getting-started-local-jmeter-and-gatling.md)

Docker is a good option if you'd like to

* try out [Flood](https://flood.io) with a minimum of setup.
* get up and running quickly and are happy to use default configuration.
* start prototyping & tuning load test plans.
* use Flood Agent with a load generator not yet supported as a local installation \(Flood Element & Selenium\)

Alternatively, using a locally installed load generator is a good option to

* operate in environments where docker is not available or not allowed.
* apply custom libraries and configuration.
* reuse existing resources.

