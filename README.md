# Introducing Flood Agent

Flood Agent is a cross-platform agent for running [Flood](https://flood.io/) load generators on your own infrastructure.

By running your own Flood Agents, you can leverage existing infrastructure and load generator tuning expertise while at the same time benefitting from Flood's Data Collection Pipeline, and the familiar Flood UI and Analytics platform.

The Flood Agent:

* Is a single binary which runs on right on your Linux, Windows or Mac machines.
* Runs equally well on your own laptop for exploration or in your organization's datacenter for full scale load testing. 
* Integrates with existing JMeter, Gatling or Flood Element installations, or
* Optionally supports Flood's own fine-tuned load generator docker images.

## Download

_Please note:_ until the first official release please grab the latest pre-release from [https://github.com/flood-io/flood-agent/releases/](https://github.com/flood-io/flood-agent/releases/tag/v1.0-beta.0)

Grab the latest binary for your platform from the [flood-agent releases page](https://github.com/flood-io/flood-agent/releases/latest).

## Requirements

* A machine running Linux, Windows 10 or MacOS
* Network connection to the flood endpoints \(see [Getting Started](getting-started.md#firewall-preparation)\)
* Either an installation of one of the supported tools \(JMeter, Gatling or Flood Element\),
* Or docker to use one of the flood load generator docker images.

