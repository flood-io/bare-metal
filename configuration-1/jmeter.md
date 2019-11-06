---
description: Setting up and using JMeter with Flood Bare Metal
---

# JMeter

## Requirements

* Java 8
* JMeter [https://jmeter.apache.org/download\_jmeter.cgi](https://jmeter.apache.org/download_jmeter.cgi)
* Flood JMeter Plugin jar

## Installation

Install java and jmeter as-per instructions [https://jmeter.apache.org/download\_jmeter.cgi](https://jmeter.apache.org/download_jmeter.cgi).

Download the latest `flood-jmeter.jar` and `json-simple.jar` from the [flood-agent release page](https://github.com/flood-io/flood-agent/releases/latest).

\(Again, until we have an official release, please look for the latest pre-release: [https://github.com/flood-io/flood-agent/releases](https://github.com/flood-io/flood-agent/releases)\)

Put `flood-jmeter.jar` and `json-simple.jar` in `$JMETER_HOME/lib/ext`

## Agent Configuration

The minimal configuration is:

{% tabs %}
{% tab title="Linux & Mac" %}
```
tools:
  jmeter:
    jmeter_home: /path/to/jmeter
```
{% endtab %}

{% tab title="Windows" %}
```
tools:
  jmeter:
    jmeter_home: C:\Path\To\Jmeter
```
{% endtab %}
{% endtabs %}

Additionally you can add additional JMeter and JVM parameters

```
tools:
  jmeter:
    jmeter_home: ~/tmp/jmeter
    jvm_args: |
      -Xms512m
    jmeter_params: |
      testing=true

```

## Using Docker

For JMeter \(and all supported tools\) - there is the option to use our actual Flood Docker image if you do not wish to setup a local native tool binary install. Simply use the following properties in your `config.yaml` to let Flood know that you wish to use Flood's docker container for the respective load test tool instead of your own.

```
tools: 
   flood-element: true 
   gatling: true 
   jmeter: true
```





