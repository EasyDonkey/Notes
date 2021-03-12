# General

## Controls
| Command | Description |
| --- | --- |
| `shutdown 0` | Shutdown now |
| `shutdown -r 0` \| `reboot` | Reboot now |

## Miscellaneous
| Linux Command | Windows Command | Description |
| --- | --- | --- |
| `<command> --help` | `<command> /?` | Help menu |

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
| `systemctl list-units` | Active and available units in memory |
| `systemctl list-units --all` | All units in memory |
| `systemctl list-units --type <type> --state <state>` | Units in memory of type service, socket or target with state active, disabled, enabled, failed or running 
| `systemctl list-units --all --type=mount` | All mounts |
| `systemctl list-units-files` | Installed units |
| `systemctl list-units-files --type <type> --state <state>` | Installed units of type service, socket or target with state active, disabled, enabled, failed or running |
| `systemctl list-jobs` | Running jobs |
| `systemctl list-dependencies` | All dependencies |
| `systemctl isolate <target>.target` | Replace current target |
| `systemctl start debug-shell.service` | Start a virtual terminal as a logged-in root user on tty9 |

# Users and Groups

## Logging
| Command | Description |
| --- | --- |
| `last` | Login history |
| `w` | Currently logged in users |

## Management
| Command | Description |
| --- | --- |
| `sudo passwd <user>` | Change Password |

## Permissions
