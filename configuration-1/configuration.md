# Configuring Flood Agent

Agent configuration has three sources, applied in order of priority

1. flags
2. environment variables
3. the configuration file

Flags take highest precedence, followed by environment variables and then the config file.

The different sources can each be useful in different automated configuration management approaches. \(For example, you may choose to produce a static configuration file for all agent installations, and override values on specific hosts using environment variables.\)

| Flag | Env Var | Config file | Description |
| :--- | :--- | :--- | :--- |
| `--token` | `FLOOD_API_TOKEN` | `flood_api_token` | Your flood API token |
| `--grid` | `GRID_NAME` | `grid_name` | The grid name |
| `--config` |  |  | An alternative path for the config file |

## Config file

To get started, simply drop a file called `config.yaml` file in the same directory as flood-agent.

If you need it, the config system is fairly flexible. Read on below for details.

## Tool config

Tool specific config is more detailed, and so can only be specified in the config file.

Tools are not automatically detected. To generate load using a particular tool, you must first set it up in the config file.

For details please see the tool-specific page:

* [JMeter](jmeter.md)
* [Gatling](gatling.md)
* [Flood Element](flood-element.md)

### Config file details

Config files may be specified in any of JSON, TOML, YAML, HCL, envfile and Java Properties formats.

The format is determined from the file extension: "json", "toml", "yaml", "yml", "properties", "props", "prop", "hcl", "dotenv", "env"

_TODO_ pare down useful/common formats. Some formats don't do nesting.

The config file is searched for in a number of standard locations:

1. `/etc/flood-grid/config/config.{ext}`
2. `$HOME/.config/flood-grid/config.{ext}`
3. `./config.{ext}` \(the current directory\)

