# General

## Controls
| Command | Description |
| --- | --- |
| `shutdown 0` | Shutdown now |
| `shutdown -r 0` \| `reboot` | Reboot now |

## Miscellaneous
| Command | Description |
| --- | --- |
| `date -d @<Unix epoc timestamp>` | Print date format from Unix epoc timestamp (seconds till 01.01.1970) |

## Resources
| Command | Description |
| --- | --- |
| `free -h` | Memory usage |

# Hardware

## Information
| Command | Description |
| --- | --- |
| `cat /proc/partitions` | All SCSI devices (also virtual) |
| `sudo dmidecode` | BIOS |
| `hdparm -I </path/to/disk>` | Disks |
| `lscpu` | CPU |
| `lspci` | PCI devices |
| `lsscsi -v` | SCSI devices |
| `lsusb` | USB devices |

# Processes

## systemctl
| Command | Description |
| --- | --- |
| `systemctl list-units` | Current loaded units |
| `systemctl list-jobs` | Current running jobs |
| `systemctl list-dependencies` | All dependencies |
| `systemctl isolate <target>.target` | Replace current target |
| `systemctl start debug-shell.service` | Start a virtual terminal as a logged-in root user on tty9 |

# Users and Groups

## Logging
| Command | Description |
| --- | --- |
| `last` | Login history |
