# Overview
1. General

# General

## System Information
`$ cat /etc/os-release`

## Manual Pages

### Manual Page for Manual Pages :-)
`$ man man`

#### Sections
| Number | Description |
| --- | --- |
| 1 | Executable programs or shell commands |
| 2 | System calls (functions provided by the kernel) |
| 3 | Library calls (functions within program libraries) |
| 4 | Special files (usually found in /dev) |
| 5 | File formats and conventions eg /etc/passwd |
| 6 | Games |
| 7 | Miscellaneous (including  macro  packages  and  conventions), e.g. man(7), groff(7) |
| 8 | System administration commands (usually only for root) |
| 9 | Kernel routines (non standard) |

### Usage
`$ man <application>`
- <application> can also be a sub-part of an application like apt-cache and apt-get for the apt application

### Search the Manual Pages
`$ man -k <keyword> | grep <section number> | grep <additional keyword>`
- grep for the `<section number>` is optional

### Update Man Pages
`$ sudo mandb`

# File System

## Hierarchy
`$ man hier`

## Libraries
Libraries are stored in /lib.

### Add non-standard Library
`$ sudo vim /etc/ld.so.conf`
`$ sudo ldconfig -v: Update library cache`
