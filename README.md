# FileGuard - File Integrity Checker

A powerful tool to monitor changes in files by calculating and comparing hash values. Ensure the integrity of your critical files and detect unauthorized modifications.

## Features

- **Multiple Hash Algorithms**: Support for MD5, SHA-1, and SHA-256 algorithms
- **Baseline Creation**: Store initial file states for future comparison
- **Integrity Checking**: Detect any changes to monitored files
- **Detailed Reporting**: Get comprehensive reports on file modifications
- **Flexible Configuration**: Monitor specific files or entire directories
- **Performance Optimized**: Efficient scanning of large file systems

## Installation

```bash
npm install -g file-integrity-checker
```

## Usage

### Create a baseline

```bash
node src/main.js baseline /path/to/monitor --algorithm sha256 --recursive
```

### Check integrity against baseline

```bash
node src/main.js check /path/to/monitor --algorithm sha256
```

### View current status

```bash
node src/main.js status
```

## Options

- `-a, --algorithm <algorithm>`: Hash algorithm to use (md5, sha1, sha256)
- `-r, --recursive`: Scan directories recursively
- `-e, --exclude <patterns>`: Comma-separated list of patterns to exclude
- `-q, --quiet`: Only show changed files (for check command)

## Examples

Create a baseline of a directory, excluding temporary files:

```bash
node src/main.js baseline /important/files --exclude .tmp,.bak,node_modules
```

Check integrity, showing only modified files:

```bash
node src/main.js check /important/files --quiet
```

## Use Cases

- Monitoring critical system files for unauthorized changes
- Verifying software installation integrity
- Ensuring configuration files remain unchanged
- Detecting malware modifications to system files
- Validating backups and archives

## License

MIT