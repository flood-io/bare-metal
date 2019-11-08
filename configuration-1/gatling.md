---
description: Setting up and using Gatling with Flood Bare Metal
---

# Gatling

## Requirements <a id="requirements"></a>

* Java 8
* Gatling [https://gatling.io/open-source](https://gatling.io/open-source)

## ‌Installation

‌Install Gatling by downloading and extracting the `gatling-charts-highcharts-bundle-3.x.x-bundle.zip` file onto your node.‌

Verify that Gatling is able to be run from the command line by using `./gatling.sh` from the Gatling `bin` directory. If you are able to run the default example `computerdatabase.BasicSimulation` then you have successfully setup the tool!

## Agent Configuration <a id="agent-configuration"></a>

‌The next step is to configure your `config.yaml` file to tell the Flood Agent to use this Gatling installation specifically.

The minimal configuration used for this is:

```text
tools:  
   gatling:    
      gatling_home: ~/gatling-charts-highcharts-bundle-3.x.x-bundle
```

## Using Docker

For Gatling \(and all supported tools\) - there is the option to use our actual Flood Docker image if you do not wish to setup a local native tool binary install. Simply use the following properties in your `config.yaml` to let Flood know that you wish to use Flood's docker container for the respective load test tool instead of your own.

```text
tools:    
   flood-element: true    
   gatling: true    
   jmeter: true
```

​

