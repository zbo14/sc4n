# sc4n

A CLI that takes a list of domains and scans IP addresses, vhosts, and web paths in parallel.

**WARNING:** don't use this tool to scan domains you aren't authorized to scan!

## Install

Clone the repo and `cd` into it.

`sc4n` requires [nmap](https://nmap.org/) so make sure that's installed as well.

## Usage

```
_______________________________________/\\\__________________
 _____________________________________/\\\\\__________________
  ___________________________________/\\\/\\\__________________
   __/\\\\\\\\\\_____/\\\\\\\\______/\\\/\/\\\_____/\\/\\\\\\___
    _\/\\\//////____/\\\//////_____/\\\/__\/\\\____\/\\\////\\\__
     _\/\\\\\\\\\\__/\\\__________/\\\\\\\\\\\\\\\\_\/\\\__\//\\\_
      _\////////\\\_\//\\\________\///////////\\\//__\/\\\___\/\\\_
       __/\\\\\\\\\\__\///\\\\\\\\___________\/\\\____\/\\\___\/\\\_
        _\//////////_____\////////____________\///_____\///____\///__

          Pr0grammed by zbo14 with 🤖 and ❤️


USAGE: ./sc4n [OPTIONS] [file]

OPTIONS:
  -h  log usage information and exit
  -n  number of scanner processes to spawn (default: 10)
  -o  path to output directory
  -p  port list for nmap scans (default: ./lists/ports.txt)
  -q  don't print banner or info
  -w  word list for web path discovery (default: ./lists/paths.txt)
```

`sc4n` accepts a *regular* file with 1 domain per line, otherwise it reads domains from stdin.

`nmap` requires root privileges to run a [SYN scan](https://nmap.org/book/synscan.html). To avoid having to repeatedly enter your password while the script runs, you can add the following to `/etc/sudoers` (or a file in `/etc/sudoers.d/`) with `visudo`:

```
<user> ALL=NOPASSWD: /usr/bin/nmap
```

**WARNING:** be careful not to corrupt the file!
