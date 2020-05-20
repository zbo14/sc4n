# sc4n

A CLI that takes a list of domains and scans IP addresses, vhosts, and web paths in parallel.

**WARNING:** don't use this tool to scan domains you aren't authorized to scan!

## Install

Clone the repo and `cd` into it.

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
  -n  number of scanner processes to spawn (default: 20)
  -o  path to output directory
  -p  port list for nmap scans (default: ./lists/ports.txt)
  -q  don't print banner or info
  -w  word list for web path discovery (default: ./lists/paths.txt)
```

`sc4n` accepts a *regular* file containing 1 domain per line, otherwise it reads domains from stdin.
