---
description: An eagle's eye overview of how Flood Agent works
---

# How it works

## Getting to know the components

### Grids

A "grid" is a group of flood agents running on any type of computer \(for example a laptop or a cloud-managed VM instance\).

#### Agents with the same name are part of the same grid

If you're working on a single machine \(your laptop for example\) you can let flood-agent pick a random name.

If you're organising a larger grid on your own cluster of servers, pick a name to associate the nodes together.

```text
# ec2 instance 1aws-ec2-1 $ ./flood-agent --name aws-grid-1# ec2 instance 2aws-ec2-2 $ ./flood-agent --name aws-grid-1
```

#### Machines running in the same Grid should be homogeneous \(though it isn't mandatory\)

e.g. using a laptop and an extra-large VM instance would make test results difficult to interpret / trust.

### Floods

A flood is an instance of a load test. It is scheduled onto one or more grids.

&lt;TODO screenshot of a flood in the ui&gt;

