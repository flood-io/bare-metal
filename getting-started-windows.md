---
description: >-
  This quick start guide will show you how to run Flood Agent on Windows using
  your own machine.
---

# Getting Started on Windows

## Download and Install

The guide shows you how to run ad-hoc instances, suitable for exploration & prototyping floods. For production-scale installations see [Running with NSSM \(Windows\)](deployment/running-with-nssm-windows.md).

## Download

We recommend downloading the agent into its own directory. For the guide, let's assume you've chosen to use `c:\flood-agent`:

![](.gitbook/assets/flood-agent-windows-install%20%281%29.png)

{% hint style="success" %}
In the console, to run a binary from the current directory, don't forget the `.\`

For example, to run Flood Agent: `.\flood-agent.exe`
{% endhint %}

## Preparing the load generator

To start running load tests with Flood Agent, you must first prepare the load generator.

On Windows we support JMeter and Gatling, either by adding a Flood plugin to your existing installation, or by using one of our pre-built bundles.

For detailed instructions, take a look at [Getting Started - Local JMeter & Gatling](getting-started-local-jmeter-and-gatling.md)

