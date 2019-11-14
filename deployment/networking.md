# Networking

Flood agent requires access to several endpoints to operate.

To verify network connectivity, please use the `flood-agent check` command.

If you discover that connectivity is limited, please contact your operations staff. 

Your internal network may already have a web proxy which you can use. For more details see [Integrating with a web proxy](integrating-with-a-web-proxy.md).

## Endpoints

The machine running `flood-agent` must have access to the following endpoints:

* https://drain.flood.io
* https://beacon.flood.io
* https://vault.flood.io
* https://flood-archives.s3-accelerate.amazonaws.com
* https://logs.us-east-1.amazonaws.com
* https://sns.\*.amazonaws.com
* https://sqs.\*.amazonaws.com

