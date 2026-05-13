# PortScanner

A fast TCP port scanner written in Python, using multithreading to scan multiple ports simultaneously.

> This project was built following the [Hackstation tutorial](https://www.youtube.com/watch?v=255EwoaAcDk&t=3289s), with some additions made by me.

## Features

- Scans top 1000 most common ports (default)
- Scans top 10000 most common ports (`--top-10k`)
- Scans all 65535 ports (`--all`)
- Auto-detects timeout via ping
- Service name detection per port (e.g. `80 → http`, `22 → ssh`)
- Multithreaded for fast scanning
- Save results to a file (`-o`)

## Requirements

```bash
pip install pythonping
```

> **Note:** `pythonping` requires root/administrator privileges to run.

## Usage

```bash
sudo python PortScanner.py -t <target> [options]
```

### Options

| Flag | Description |
|------|-------------|
| `-t`, `--target` | Target IP or domain (required) |
| `--top-10k` | Scan top 10k ports instead of top 1k |
| `--all` | Scan all 65535 ports |
| `--threads` | Number of worker threads (default: 30) |
| `--timeout` | Timeout in ms per port (default: auto via ping) |
| `-o`, `--output` | Save open ports to a file |

### Examples

```bash
# Scan top 1000 ports
sudo python PortScanner.py -t scanme.nmap.org

# Scan top 10k ports and save results
sudo python PortScanner.py -t scanme.nmap.org --top-10k -o results.txt

# Scan all ports with 50 threads
sudo python PortScanner.py -t scanme.nmap.org --all --threads 50
```

## Credits

Based on the tutorial by [Hackstation](https://www.youtube.com/watch?v=255EwoaAcDk&t=3289s).
