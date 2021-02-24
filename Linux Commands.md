# General

## Miscellaneous
| Command | Description |
| --- | --- |
| `date -d @<Unix epoc timestamp>` | Print date format from Unix epoc timestamp (seconds till 01.01.1970) |

## Resources
| Command | Description |
| --- | --- |
| `free -h` | Memory usage |

# Processes

## systemctl
| Command | Description |
| --- | --- |
| `systemctl list-units` | List current loaded units |
| `systemctl list-jobs` | List current running jobs |
| `systemctl list-dependencies` | List all dependencies |
| `systemctl isolate <target>.target` | Replace current target |
| `systemctl start debug-shell.service` | Start a virtual terminal as a logged-in root user on tty9 |
