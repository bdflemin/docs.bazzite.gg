---
title: Installing Arctis Manager
authors:
  - "@elegos"
  - "@ifeign"
  - "@rdamron"
tags:
  - Community
search:
  exclude: true
---

# Installing Arctis Manager

## Purpose
This guide walks you through installing [Linux-Arctis-Manager](https://github.com/elegos/Linux-Arctis-Manager) (v2.0.4+) using Distrobox. This method keeps your host system immutable while providing the manager with necessary hardware access and background services. For a list of currently supported devices as well as advanced documentation, please check the linked repository.

## Run install script
The following script will prepare the Distrobox container, build the app and set the necessary permissions on the host system. This Distrobox executes applications within containers, mounting `/var`, `/etc` and your `/home` directories in the container itself. Arctis Manager heavily relies on your `/home` directory, thus the container is not really used but for the installation process and is not as self-contained as other Distrobox apps.

```bash
curl -LsSf https://raw.githubusercontent.com/elegos/Linux-Arctis-Manager/refs/heads/develop/scripts/distrobox.sh | sh
```

### Verification (Optional)
To verify the daemon is running and can see your device, run this on your host
```bash
lam-cli devices list
```

## Autostart the tray app (Optional)
To have the tray icon appear automatically on login, create a manual autostart entry on the host.
### Copy the systray .desktop file to the autostart folder
```bash
cp ~/.local/share/applications/ArctisManagerSystray.desktop ~/.config/autostart/
```
