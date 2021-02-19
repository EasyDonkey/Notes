####################################################################################<br>
<b>This document relates to Debian / Ubuntu and some parts may greatly differ to RedHat, Suse etc..</b><br>
####################################################################################<br>



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
- `| grep <section number>` is optional

### Update Man Pages Database
`$ sudo mandb`
- This is usually done automagically when software is installed / removed

### Documentation Files
Programs and packages may have extensive documentation files in `/usr/share/doc` resp. `/usr/share/doc/packages`.

## Useful Commands
| Command | Description |
| --- | --- |
| `$ locate --basename <keyword>` | Find an executable by base name |
| `$ which <keyword>` | Locate a command |

### Find
Find is very powerful and `$ man find` is definitely worth a read.
| Command | Description |
| --- | --- |
| `$ find <directory> -name "<keyword>" -type f` | Search files (`-type f`) |
| `$ find <directory> -size -10M -type f` | Search files smaller than 10MB |
| `$ find / -perm -4000 2>/dev/null` | Search all files with the SUID bit set and send all error messages to /dev/null |

`$ find <directory> -type f -exec grep -l <keyword> {} \; -exec cp {} ~ \; 2>/dev/null`
  - `find <directory> -type f`: Find all files in `<directory>`
  - `-exec grep -l <keyword> {} \;`: Execute grep, list all files matching the `<keyword>` regex and store them for further handling
    - `\;`: Is mandatory at the end of the `-exec` flag
  - `-exec cp {} ~ \;`: Copy the files from {} in the user's home directory
  - `2>/dev/null`: Supress all error messages (mostly "Permission denied") by sending them to /dev/null

## System Wide Environment Variables
Are stored in `/etc/environment` as key=value pairs.

# File System

## Hierarchy
`$ man hier`

## Disk Space Usage
`$ df -h`

## SSD Health

### fstrim
`$ sudo fstrim -Av`
- Check and discard unused blocks (should be done regularly)

## Archive Handling with tar

### Archiving vs. Compression
Archiving is taking multiple directories and files and put them into a single file while compression is trying to reduce the file size through algorithms which look for repeating pattern to save space.

### Create and Compress an Archive
`$ tar -zcvf <name>.tar.gz <directory to archive>`
  - `-z`: Zip (compress) with gzip
  - `-c`: Create a new archive
    - Directories are archived recursively
  - `-v`: Verbose, meaning one line of output for each file
    - Should be left out for large archives on a remote machine
  - `-f`: Name for the archive file (must be the last argument)
  - `.tar.gz`: Nice way to let others know it is a compressed archive (optional)

### Extract and Decompress an Archive
`$ tar -zxvf <file> -C <path/to/extract/to>`
  - `-z`: Unzip (decompress) with gzip
  - `-x`: Extract
  - `-C`: Specify the destination path (optional)

### Take a Look at the Archive
`$ tar -tvf <file> | less`
  - `-t`: List the contents of the archive

### Important to Remember
tar overwrites files while extracting, thus these points should be kept in mind:
1. When creating an archive always archive it from the corresponding root directory
    - E.g. 20 files in /foo: Archive the /foo directory and not directly all files inside /foo
2. To protect against overwriting the `-k` and `--no-overwrite-dir` flags should be used
3. If in doubt extract an archive into an empty directory

## Dynamic and Static Configurations
Dynamic configuration (free to be modified by the administrator): /etc/<br>
Static configuration (should not be touched): /usr/lib/

## Libraries
Libraries are stored in /lib.

### Add non-standard Library
`$ sudo vim /etc/ld.so.conf`<br>
`$ sudo ldconfig -v: Update library cache`
