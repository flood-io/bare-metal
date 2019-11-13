---
description: Setting up and using Flood Element with Flood Agent
---

# Flood Element

## Requirements

#### Linux / Unix

* NPM
* latest version of [node.js](https://nodejs.org)

#### OS X

* Brew \(recommended\) or NPM
* latest version of [node.js](https://nodejs.org)

#### Windows

* [Chocolatey](https://chocolatey.org)
* latest version of [node.js](https://nodejs.org)

## Installation

Please refer to our Flood Element sub-site with full installation instructions for each supported environment - [https://element.flood.io](https://element.flood.io)

Install Element using our `stable` or `beta` builds using the following:

| Build type | Installation string |
| :--- | :--- |
| `stable` | `npm install -g @flood/element-cli` |
| `beta` | `npm install -g @flood/element-cli@beta` |

## Agent Configuration <a id="agent-configuration"></a>

The next step is to configure your `config.yaml` file to tell the Flood Agent to use your local Element installation specifically.

The minimal configuration used for this is:

```text
tools:  
   flood-element: true
```

If Element is not detected to be installed locally and Docker is detected then the Flood Agent will attempt to use Flood's publicly available Docker image.

## Using Docker

For Flood Element \(and all supported tools\) - there is the option to use our actual Flood Docker image if you do not wish to setup a local native tool binary install. 

If Flood Element is not detected to be installed locally and Docker is detected then the Flood Agent will attempt to use Flood's publicly available Docker image automatically.

```text
tools:    
   flood-element: true    
   gatling: true    
   jmeter: true
```

