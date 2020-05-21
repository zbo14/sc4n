# sc4n

A CLI that takes a list of domains and scans IP addresses, vhosts, and web paths in parallel.

**WARNING:** don't use this tool to scan domains you aren't authorized to scan!

## Install

Clone the repo, `cd` into it, and run `git submodule update --init`.

`sc4n` also requires [ffuf](https://github.com/ffuf/ffuf) and [nmap](https://nmap.org/) so make sure those are installed.

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
  -p  number of top ports to scan (default: 1000)
  -q  don't print banner or info
  -w  word list for web paths (default: ./lists/paths.txt)
  -z  word list for virtual hosts (default: ./lists/hosts.txt)
```

`sc4n` accepts a *regular* file with 1 domain per line, otherwise it reads domains from stdin.

`nmap` requires root privileges to run a [SYN scan](https://nmap.org/book/synscan.html). To avoid having to repeatedly enter your password, you can add the following to `/etc/sudoers` (or a file in `/etc/sudoers.d/`) with `visudo`:

```
<user> ALL=NOPASSWD: /usr/bin/nmap
```

**WARNING:** be careful not to corrupt the file!
