# linux portable file Version COntrol (vco)

<img width="624" height="458" alt="image" src="https://github.com/user-attachments/assets/9f7ee579-dcf7-4f19-a267-62377bb2a984" />


Enterprise-grade, POSIX-compliant Bash script for local file versioning. It replaces standard text editors by managing checkouts, checkins, locks, and differential comparisons within a transparent `.vc` hidden directory.

## Core Features
*   **Zero-Dependency History:** Tracks file versions locally in `.vc/` without requiring Git or SVN.
*   **Automatic Shebang Detection:** Appends revision comments directly beneath `#!/bin/bash` or other interpreter headers without breaking execution.
*   **Syslog Integration:** All critical actions (checkout, checkin, revert, delete) are logged to the system journal via `logger -t vc`.
*   **Dynamic Dependency Resolution:** Automatically detects missing comparison binaries (`colordiff`, `git`) and invokes `apt-get`, `dnf`, or `yum` to install them if requested.
*   **Strictly Numeric Navigation:** Terminal interfaces map dynamically to array lengths, removing string-parsing vulnerabilities.
*   Flexible options for editors & diff tools.

## Installation

1. Clone the repo `git clone https://github.com/meirlazar/VCO_SCRIPT.git`
2. Make vco executable `cd VCO_SCRIPT/; chmod +x vco`
3. Copy vco into your path `sudo cp vco /usr/local/bin/vco`

## Usage
1. Instead of using your normal editor like vi/vim to edit a file, use vco. `vco filename`
2. Use vco to move, delete, rename etc to safely move,remove, or rename your version history
3. Menu driven for check-out, check-in, revert changes, compare versions, etc.
4. All revisions stored locally in the directory that the file exists in under .vc/
5. Make an alias to "force" yourself to use the vco tool. Add this to your ~/.bashrc `alias vim='/usr/local/bin/vco'` 

