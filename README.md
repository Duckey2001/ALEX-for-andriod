PyMobileDevice3
Python application Pypi version Downloads Discord Ask DeepWiki

Overview
pymobiledevice3 is a pure Python 3 implementation for interacting with iOS devices (iPhone, iPad, ...). It includes both a CLI and a Python API and is supported on:

Windows
Linux
macOS
Main features:

Device discovery over bonjour
TCP port forwarding
Syslog and oslog streaming
Profile and application management
AFC file access
Crash report collection
Network sniffing (PCAP)
Firmware update
Recovery/DFU workflows
Notification listen/post (notify_post())
Querying and setting SpringBoard options
WebInspector automation
DDI/DVT developer tooling
Backup and restore
Quick Start
Install from PyPI:

python3 -m pip install -U pymobiledevice3
Or install from source:

git clone git@github.com:doronz88/pymobiledevice3.git
cd pymobiledevice3
python3 -m pip install -U -e .
Verify connectivity and run first commands:

pymobiledevice3 usbmux list
pymobiledevice3 syslog live
pymobiledevice3 apps list
Platform Notes
Windows:

Install iTunes from Microsoft Store: https://apps.microsoft.com/detail/9pb2mz1zmb1s?hl=en-US&gl=US

For WSL2, enable mirrored networking mode: https://learn.microsoft.com/en-us/windows/wsl/networking#mirrored-mode-networking

[wsl2]
networkingMode=mirrored
Linux:

Install usbmuxd: https://github.com/libimobiledevice/usbmuxd
OpenSSL:

OpenSSL is explicitly required for older iOS versions (< 13).
Recovery/DFU support

Requires libusb.
Support Matrix (Developer Services)
iOS >= 17 developer services require tunnel-based transport.

Host OS	iOS 17.0-17.3.1	iOS 17.4+
macOS	Supported	Supported
Windows	Supported (requires additional drivers)	Supported
Linux	Limited	Supported (lockdown tunnel)
See the detailed guide: iOS 17+ tunnels

Common CLI Tasks
See full recipes: CLI recipes

# List connected devices
pymobiledevice3 usbmux list

# Watch syslog
pymobiledevice3 syslog live

# Pull crash reports
pymobiledevice3 crash pull /path/to/crashes

# Mount DDI
pymobiledevice3 mounter auto-mount

# DVT screenshot (requires developer setup)
pymobiledevice3 developer dvt screenshot /path/to/screen.png
Install shell completions:

pymobiledevice3 install-completions
Python API and Protocol Internals
Protocol overview: Understanding iDevice protocol layers
DTX API quick start: DTX README
DTX internals: DTX DEVELOPMENT
RemoteXPC internals: RemoteXPC
Building custom CLI commands with service_provider: Guide
