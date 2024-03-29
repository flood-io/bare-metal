---
description: Setting up and using JMeter with Flood Agent
---

# Configuring JMeter

## Installation

### All in one bundle

The simplest way to run JMeter is to use our all in one bundle.

* install Java JRE 8+
* download the latest bundle: [flood-jmeter-bundle-5.1.1.zip](https://flood-binaries.s3-accelerate.amazonaws.com/flood-jmeter/canary/5.1.1/flood-jmeter-bundle-5.1.1.zip)
* unzip the bundle to e.g. `~/flood-jmeter`

### Flood JMeter Plugin

If you already have JMeter installed, you only need to add the Flood JMeter Plugin to start testing with Flood

* download the latest Flood JMeter jar: [flood-jmeter-5.1.1.jar](https://flood-binaries.s3-accelerate.amazonaws.com/flood-jmeter/canary/5.1.1/flood-jmeter-5.1.1.jar).
* copy `flood-jmeter-5.1.1.jar`  to the JMeter extensions directory \(i.e. `$JMETER_HOME/lib/ext`\)

## Agent Configuration

The minimal configuration is:

{% tabs %}
{% tab title="Linux & Mac" %}
```yaml
tools:
  jmeter:
    jmeter_home: /path/to/jmeter
```
{% endtab %}

{% tab title="Windows" %}
```yaml
tools:
  jmeter:
    jmeter_home: C:\Path\To\Jmeter
```
{% endtab %}
{% endtabs %}

If required, you can add custom JMeter and JVM parameters:

```text
tools:
  jmeter:
    jmeter_home: ~/tmp/jmeter
    jvm_args: |
      -Xms512m
    jmeter_params: |
      -Jtesting=true

```

## Using Docker \(linux & macOS only\)

For JMeter \(and all supported tools\) - there is the option to use our actual Flood Docker image if you do not wish to setup a local native tool binary install. Simply use the following properties in your `config.yaml` to let Flood know that you wish to use Flood's docker container for the respective load test tool instead of your own.

```text
tools: 
   flood-element: true 
   gatling: true 
   jmeter: true
```





