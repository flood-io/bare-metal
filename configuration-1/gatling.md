---
description: Setting up and using Gatling with Flood Agent
---

# Configuring Gatling

## ‌Installation

### All in one bundle

The simplest way to run Gatling is to use our all in one bundle.

* install Java JRE 8+
* download the latest bundle: [flood-gatling-bundle-3.3.1.zip](https://flood-binaries.s3-accelerate.amazonaws.com/flood-gatling/canary/3.3.1/flood-gatling-bundle-3.3.1.zip).
* unzip the bundle to e.g. `~/flood-gatling`

### Flood Gatling Plugin

If you already have Gatling installed, you only need to add the Flood Gatling Plugin jars to start testing with Flood.

{% hint style="warning" %}
Note that flood-gatling minimally modifies your Gatling installation. You may wish to take a copy of `$GATLING_HOME` before adding flood-gatling
{% endhint %}

* download the latest flood-gatling zip: [flood-gatling-jars-3.3.1.zip](https://flood-binaries.s3-accelerate.amazonaws.com/flood-gatling/canary/3.3.1/flood-gatling-jars-3.3.1.zip)
* unzip & move the jars into `$GATLING_HOME/lib`
* edit `$GATLING_HOME/conf/gatling.conf`

{% tabs %}
{% tab title="conf/gatling.conf" %}
```text
gatling {
  ...  
  data {
    writers = [file, flood] # add flood to the list of writers
  }
}
```
{% endtab %}
{% endtabs %}

## Agent Configuration <a id="agent-configuration"></a>

‌The next step is to configure your `config.yaml` file to tell the Flood Agent to use this Gatling installation specifically.

The minimal configuration used for this is:

```text
tools:  
   gatling:    
      gatling_home: /path/to/gatling
```

## Using Docker \(linux & macOS only\)

For Gatling \(and all supported tools\) - there is the option to use our actual Flood Docker image if you do not wish to setup a local native tool binary install. Simply use the following properties in your `config.yaml` to let Flood know that you wish to use Flood's docker container for the respective load test tool instead of your own.

```text
tools:    
   flood-element: true    
   gatling: true    
   jmeter: true
```

​

