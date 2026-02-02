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

---

## push-pkg - One-Click Package Publisher

Push RPM/DEB packages to Linux Hardened repos from any machine.

### Install

```bash
mkdir -p ~/bin
curl -sL https://raw.githubusercontent.com/rushikeshsakharleofficial/deb-repos/main/push-pkg -o ~/bin/push-pkg
chmod +x ~/bin/push-pkg
export PATH="$HOME/bin:$PATH"
```

### Usage

```bash
push-pkg mypackage.deb    # Push to deb.linuxhardened.com
push-pkg mypackage.rpm    # Push to rpm.linuxhardened.com
```

### Features

- Auto-clones repos if not present
- Auto-pulls latest changes before pushing
- Detects architecture from package metadata (with filename fallback)
- Generates directory index pages
- Updates repo metadata (dpkg-scanpackages / createrepo_c)
- Commits and pushes to GitHub

### Dependencies

**For DEB packages:**
```bash
sudo apt install dpkg-dev git
```

**For RPM packages:**
```bash
sudo apt install createrepo-c git
```

### How It Works

1. Detects package type (.rpm or .deb)
2. Extracts package name and architecture
3. Copies to correct directory (`pool/main/{letter}/` for DEB, `packages/{arch}/{letter}/` for RPM)
4. Updates repository metadata
5. Regenerates HTML index pages
6. Commits and pushes to GitHub
