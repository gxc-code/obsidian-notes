# systemctl

Managing a linux system with`systemd`.

Uses systemd *units*:
	- foo.service
	- foo.mount
	- foo.socket
	- foo.timer
	- foo.automount

**Check Status**:
```bash
sudo systemctl status foo.service
```

**Start/Stop**:
```bash
sudo systemctl start foo.service
sudo systemctl stop foo.service
```

**Enable/Disable (Start on boot):**
```bash
sudo systemctl enable foo.service
sudo systemctl disable foo.service

# Options
--now # Start/Stop now
```

**Restart/Reload:**
```bash
# Restart unit
sudo systemctl restart foo.service

# Reload unit config
sudo systemctl reload foo.service
```

**Read/Edit**
```bash
sudo systemctl cat foo.service

sudo systemctl edit foo.service

# Options (edit)
--full # edit full copy of file
--runtime # edit unit file until next reboot
```

**List Units:**
```bash
sudo systemctl list-units

sudo systemctl list-sockets

sudo systemctl list-timers

# Options
--type=<type>
--state=<state>
```

**Mask/Unmask Unit (Mask=Prevent Start):**
```bash
sudo systemctl mask foo.service
sudo systemctl unmask foo.service
```

**Get/Set default target:**
```bash
sudo systemctl get-default
sudo systemctl set-default foo.target
```

**Isolate/Switch to different target:**
```bash
sudo systemctl status foo.target
```

**Remotely execute systemctl commands:**
```bash
# Uses SSH
sudo systemctl -H root@server restart foo.service
```

**Show man page for unit:**
```bash
sudo systemctl help foo.service
```

**List installed unit files:**
```bash
sudo systemctl list-unit-files
```

**System manager reload/reexecute:**
```bash
# Reload system manager config
sudo systemctl daemon-reload

# Reexecute system manager
sudo systemctl daemon-reexec
```