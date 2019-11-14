# Configuring Flood Agent

There are a few different ways of configuring flood-agent though you don't need to know all of them. These options are provided to make life easier for advanced users and operations teams.

To get started, use the guided `flood-agent configure` configuration wizard, or drop a file called `config.yaml` file into the same directory as flood-agent.

If you need it, the config system is fairly flexible. Read on below for details.

## Configuration basics

Agent configuration has three sources, applied in order of priority

1. flags
2. environment variables
3. the configuration file

Flags take highest precedence, followed by environment variables and then the config file.

The different sources can each be useful in different automated configuration management approaches. 

For example, you may choose to produce a base static configuration file for all agent installations, and override values on specific hosts using environment variables.

| Flag | Env Var | Config file | Description |
| :--- | :--- | :--- | :--- |
| `--token` | `FLOOD_API_TOKEN` | `flood_api_token` | Your flood API token |
| `--grid` | `GRID_NAME` | `grid_name` | The grid name |
| `--config` |  |  | An alternative path for the config file |

## Tool config

Tool specific config is more detailed, and so can only be specified in the config file.

If the tool configuration is left blank, and docker is available, the default is to use docker containers for any of available the load generators \(JMeter, Gatling, Flood Element and Selenium\).

However, only JMeter and Gatling are currently able to be run directly.

Tools are not automatically detected. To generate load using a particular tool, you must first set it up in the config file.

For details please see the tool-specific page:

* [JMeter](jmeter.md)
* [Gatling](gatling.md)

## Config file search paths

To facilitate package management and configuration management tools, the configuration file is searched for in a number of standard locations:

1. `./config.yaml` \(the current directory\)
2. `$HOME/.config/flood-grid/config.yaml`
3. `/etc/flood-grid/config/config.yaml`

