# sysfetch

A small Bash utility that prints the operating system, kernel, architecture, uptime, and shell.

## Usage

```bash
chmod +x sysfetch sysfetch.sh
./sysfetch
```

The script works on Linux and falls back to the platform's `uptime` command when `/proc/uptime` is unavailable.
