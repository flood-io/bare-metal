---
description: Follow these simple steps to get started trying out Flood Bare Metal.
---

# Getting Started \(linux\)

For trying out the Flood Bare Metal agent follow these instructions to run a single instance on your own machine.

\(For production-scale installation see [Running with systemd \(linux\)](deployment/running-with-systemd-linux.md) \)

## Download

_Please note:_ until the first official release please grab the latest pre-release from [https://github.com/flood-io/flood-agent/releases/](https://github.com/flood-io/flood-agent/releases/tag/v1.0-beta.0)

Grab the latest binary for linux from the [flood-agent releases page](https://github.com/flood-io/flood-agent/releases/latest).

We recommend downloading the agent into its own directory:

```text
mkdir -p ~/flood-bare-metal
cd ~/flood-bare-metal
curl -L https://.../flood-bare-metal-agent-linux-x64 > flood-agent
chmod 0755 ./flood-agent
```

## Firewall preparation

Ensure that your machine has network access to the following endpoints 

* https://drain.flood.io
* https://beacon.flood.io
* https://vault.flood.io
* https://flood-archives.s3-accelerate.amazonaws.com
* https://logs.us-east-1.amazonaws.com
* https://sns.\*.amazonaws.com
* https://sqs.\*.amazonaws.com

## Flood API Token

Grab your Flood API token from [https://app.flood.io/account/user/security](https://app.flood.io/account/user/security)

![](.gitbook/assets/flood-access-token.png)

## Configure the agent

Create a configuration file `~/flood-agent/config.yaml` with the following contents:

```text
flood_api_token: flood_live_f100d1e9a8e # as grabbed above
grid_name: mygrid1
tools:
  jmeter:
    jmeter_home: /path/to/jmeter_home
```

## Run the agent

```text
./flood-agent --config config.yaml
```

Your agent will start, outputting some informational logging. The agent is organised into the flood grid `mygrid1`

If you perform the above on a second machine, your grid `mygrid1` will now have two nodes. Any floods scheduled onto `mygrid1` will now run on both machines.

## Run a flood

Create a flood as normal \(or Start more like this\)

![](.gitbook/assets/test-step-1.png)

progress through the steps until Step 6, where you'll choose `mygrid1` .

![\(draft: need a better image once the UI is updated\)](.gitbook/assets/test-step-6-draft.png)

Launch the test.

