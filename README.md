# Linux Hardened DEB Repository

Custom DEB repository hosted at **https://deb.linuxhardened.com**

## Add Repository

```bash
echo "deb [trusted=yes] https://deb.linuxhardened.com stable main" | sudo tee /etc/apt/sources.list.d/linuxhardened.list
sudo apt update
```

## Install Packages

```bash
sudo apt install <package-name>
```

## Available Packages

- **global-logrotate** - Fast parallel log rotation utility
- **vib** - Backup files before editing with vim/nano
- **hello** - GNU hello example package
