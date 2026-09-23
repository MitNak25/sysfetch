# 🐱 sysfetch

> A tiny Bash system-information utility with a clean ASCII cat.

![Shell](https://img.shields.io/badge/Shell-Bash-4eaa25?logo=gnubash&logoColor=fff)
![Platform](https://img.shields.io/badge/platform-Linux%20%2B%20Unix-lightgrey)
![License](https://img.shields.io/badge/license-see%20LICENSE-blue)

## ✨ What it shows

- Operating system name from `/etc/os-release` when available.
- Kernel release.
- CPU architecture.
- Human-readable uptime.
- Current shell name.

The script is intentionally dependency-light and falls back to `uname` and `uptime` when Linux-specific files are unavailable.

## 🚀 Usage

Clone the repository and run the main executable:

```bash
git clone https://github.com/MitNak25/sysfetch.git
cd sysfetch
chmod +x sysfetch sysfetch.sh
./sysfetch
```

Both entry points produce the same output:

```bash
./sysfetch
./sysfetch.sh
```

Example output:

```text
 /\_/\\
( o.o )  sysfetch
 > ^ <
  OS           Ubuntu 24.04 LTS
  Kernel       6.8.0
  Arch         x86_64
  Uptime       2d 4h 12m
  Shell        bash
```

The exact values depend on the host system.

## 🧰 Design details

- Uses `set -euo pipefail` for safer Bash execution.
- Resolves the wrapper path relative to its own location.
- Avoids modifying the system or creating files.
- Uses `/proc/uptime` on Linux and falls back to the `uptime` command.
- Reports `Unknown` instead of failing when optional system metadata is unavailable.

## 📁 Project layout

```text
.
├── sysfetch       # Main executable
├── sysfetch.sh    # Portable wrapper entry point
├── .gitignore     # Ignored local files
└── LICENSE        # Project license
```

## 🖥️ Compatibility

Linux is the primary target. Other Unix-like systems may work when `bash`, `uname`, and `uptime` are available. `/proc/uptime` is optional because the script includes a fallback.

## 🤝 Contributing

Keep the script dependency-free where possible, preserve the readable output format, and test changes on more than one Unix-like environment before opening a pull request.

## 📄 License

See [LICENSE](LICENSE).
