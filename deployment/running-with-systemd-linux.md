# Running with systemd \(linux\)

```text
[Unit]Description=Flood AgentDocumentation=https://bare-metal.flood.ioAfter=syslog.targetAfter=network.target[Service]Type=simpleUser=flood-agentEnvironment=HOME=/var/lib/flood-agentEnvironment=FLOOD_GRID_NAME=big-grid-1ExecStart=/usr/bin/flood-agentRestartSec=5Restart=on-failureRestartForceExitStatus=SIGPIPETimeoutStartSec=10TimeoutStopSec=0KillMode=process[Install]WantedBy=multi-user.targetDefaultInstance=1
```

