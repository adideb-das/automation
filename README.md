# Auto-Start a Binary with systemd — README

This script creates and enables a **systemd** service that auto-starts your binary (or script) on boot and streams its stdout/stderr to a log file.

---

## What this repo contains

- `setup_service.py` (the code you pasted): generates a systemd unit, installs it to `/etc/systemd/system/`, enables it at boot, and starts it immediately.

---

## Requirements

- Linux with **systemd** (most modern distros)
- Python 3.7+
- Sudo privileges (to write into `/etc/systemd/system/` and run `systemctl`)
- Your target **binary/script** must exist and be executable

---

## Configure

Open the script and replace the `***` placeholders:

```python
USER = "***"                     # your Linux username, e.g., "adi"
WORKING_DIR = f"/home/{USER}/***"  # working dir, e.g., "/home/adi/myapp"
BINARY_NAME = "***"              # executable filename, e.g., "myapp" or "run.sh"
SERVICE_NAME = "***.service"     # service name, e.g., "myapp.service"
LOG_FILE = os.path.join(WORKING_DIR, "***.log")  # log filename, e.g., "myapp.log"
