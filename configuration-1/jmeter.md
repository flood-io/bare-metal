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
{% code-tabs %}
{% code-tabs-item title="config.yaml" %}
```yaml
tools:
  jmeter:
    jmeter_home: /path/to/jmeter
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}

{% tab title="Windows" %}
{% code-tabs %}
{% code-tabs-item title="config.yaml" %}
```yaml
tools:
  jmeter:
    jmeter_home: C:\Path\To\Jmeter
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}
{% endtabs %}

Additionally you can add additional JMeter and JVM parameters

```text
tools:
  jmeter:
    jmeter_home: ~/tmp/jmeter
    jvm_args: |
      -Xms512m
    jmeter_params: |
      testing=true

```



