# Running with systemd \(linux\)

```text
[Unit]
Description=Flood Agent
Documentation=https://bare-metal.flood.io
After=syslog.target
After=network.target

[Service]
Type=simple
User=flood-agent
Environment=HOME=/var/lib/flood-agent
Environment=FLOOD_GRID_NAME=big-grid-1
ExecStart=/usr/bin/flood-agent
RestartSec=5
Restart=on-failure
RestartForceExitStatus=SIGPIPE
TimeoutStartSec=10
TimeoutStopSec=0
KillMode=process

[Install]
WantedBy=multi-user.target
DefaultInstance=1
```

