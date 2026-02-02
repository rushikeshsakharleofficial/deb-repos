# Linux Hardened DEB Repository

Debian/Ubuntu packages hosted at https://deb.linuxhardened.com

## Quick Setup

```bash
sudo curl -o /etc/apt/sources.list.d/linuxhardened.list https://deb.linuxhardened.com/linuxhardened.list
sudo apt update
sudo apt install global-logrotate
```

## Available Packages

- **global-logrotate** - Fast parallel log rotation with AES-256 encryption
