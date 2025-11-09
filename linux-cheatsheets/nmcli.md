# nmcli

Manage networking on a linux device with NetworkManager running.

**Show devices/status:**
```bash
sudo nmcli dev show
sudo nmcli dev staus
```

**Show connection profiles/status**:
```bash
sudo nmcli con show 
sudo nmcli con show
```

**Bring connection profile up/down:**
```bash
sudo nmcli con up foo
sudo nmcli con down foo
```

**Create ethernet connection profile:**
```bash
sudo nmcli con add type ethernet con-name foo ifname <interface> 
```
 