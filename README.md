# PersephrakSDemo
# PersephrakShell - File Manager Backdoor Analysis & Safe Demo

## Overview

PersephrakShell.php is a sophisticated PHP-based web shell disguised as a file manager. This repository contains:

1. **Safe HTML Mockup** (`index.html`) - Pure frontend demo with zero functionality
2. **Original Backdoor Analysis** - Technical breakdown of the malicious PHP version

## Safe HTML Demo

The `index.html` file is a **100% static frontend mockup**:
- Pure HTML/CSS/JavaScript
- No server-side code or file access
- Visual simulation only (alerts on clicks)
- Safe for GitHub Pages, portfolios, client demos

Deploy instantly via GitHub Pages or any static host.

## Original Backdoor Capabilities

The authentic PersephrakShell.php provides **full server compromise**:

### File System Control
- Arbitrary file read/write/edit (including system files)
- Recursive directory creation/deletion
- Mass permission changes (`chmod 777` recursively)
- File upload with no restrictions (webshell deployment)

### Persistence Mechanisms
- Cron job injection for backdoor reinstallation
- Emergency recovery URL fetching
- Session-based authentication bypass

### Data Exfiltration
- Automated scanners for:
  - `.env` files (API keys, database passwords)
  - `database.php`, `config.php`, `db-config.php`
  - `.htaccess`, `.ini`, `.xml`, `.yaml`, `.json`, `.toml`, `.sql`
- 200-character content previews of all found files

### Evidence Destruction
- Log clearing (`/var/log/*`, cPanel logs)
- Recursive permission resets
- Mass file deletion capabilities

### Execution Features
- `shell_exec()` for arbitrary system commands
- TAR.GZ export of entire directories
- Real-time path traversal (`..` sanitization bypassed)

## Technical Implementation

**Authentication**: Argon2id hashed password (appears legitimate)

**Path Handling**:


**Malicious Functions**:
- `force_permissions()` - Sets 0777/0666 recursively
- `scan_config_files()` - Recursive config file extraction
- `shell_exec()` - Unrestricted command execution

## Attack Vector

1. Upload via vulnerable file upload
2. Access `/PersephrakShell.php`
3. Enter password → Full server control
4. Extract credentials → Lateral movement
5. Deploy persistence → Long-term access
6. Clear logs → Maintain stealth

## Detection Signatures


## Legal & Ethical Notice

This repository serves **educational and security research purposes only**:
- HTML demo demonstrates UI design safely
- Backdoor analysis helps defenders recognize threats
- **Never deploy the original PHP code**
- Report findings to affected site owners

## Deployment (Safe Demo Only)

Coded By @z0d131482700x Persephrak Red & Blue Team Security

proof: https://shorturl.at/TadQ1

This is for educational & cybersecurity purposes.
