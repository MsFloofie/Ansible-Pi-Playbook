# Ansible Pi Playbook

My Ansible Playbook I use each time I reflash my Raspberry Pi's. The playbook automates:
 - updating apt cache
 - upgrading apt packages
 - auto-removing obsolete apt packages
 - Install a list of packages
 - Create a user and add them as root
## Prerequisites

Install `ansible` on the machine you plan to run this playbook on.

Since the [ISO I use](https://raspi.debian.net/tested-images/) does not have `python3` installed by default, make sure  it's present.

This script is only built with Debian-based distro's in mind. Feel free to fork it if you want other package managers.
## Usage

1. Copy the example files to the same directory.
```sh
cp example.hosts.ini hosts.ini
cp example.vars.yml vars.yml
```
2. Add hosts to `host.ini`
3. Add or remove packages in `vars.yml`
4. Add desired username to create.
5. For the `password:` variable, run `mkpasswd --method=sha-512` in a terminal and use the output from it.
6. Run it with `ansible-playbook -K playbook.yml`
## Roadmap

 - Automatically install [Oh My ZSH](https://ohmyz.sh/#install).

 - Automatically add SSH keys