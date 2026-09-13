<p align="center">
  <img src="https://github.com/jotavare/jotavare/blob/main/42/banners/piscine_and_common_core/github_piscine_and_common_core_banner_born2beroot.png">
</p>

<p align="center">
	<img src="https://img.shields.io/badge/status-finished-success?color=%2312bab9&style=flat-square"/>
	<img src="https://img.shields.io/badge/evaluated-21%20%2F%2012%20%2F%202022-success?color=%2312bab9&style=flat-square"/>
	<img src="https://img.shields.io/badge/score-125%20%2F%20100-success?color=%2312bab9&style=flat-square"/>
	<img src="https://img.shields.io/github/languages/top/jotavare/born2beroot?color=%2312bab9&style=flat-square"/>
	<img src="https://img.shields.io/github/last-commit/jotavare/born2beroot?color=%2312bab9&style=flat-square"/>
	<a href='https://www.linkedin.com/in/jotavare' target="_blank"><img alt='Linkedin' src='https://img.shields.io/badge/LinkedIn-blue?style=flat-square'/></a>
	<a href='https://profile.intra.42.fr/users/jotavare' target="_blank"><img alt='42' src='https://img.shields.io/badge/Porto-100000?style=flat-square&logo=42&logoColor=white&labelColor=000000&color=000000'/></a>
</p>

<p align="center">
	<a href="#about">About</a> •
	<a href="#mandatory">Mandatory</a> •
	<a href="#bonus">Bonus</a> •
	<a href="#monitoring-script">Monitoring script</a> •
	<a href="#contributing">Contributing</a> •
	<a href="#license">License</a>
</p>

## ABOUT
This system administration project focuses on setting up a secure virtual machine, built on Debian under VirtualBox. It covers key topics such as virtualization, partitioning, LVM, command-line tools, SSH, and system security measures like sudo, firewalls, and password policies. The project repository includes a script for automated tasks and the virtual machine signature.

> [!NOTE]
> For the rest of the projects and exams in the cursus, <a href="https://github.com/jotavare/42-common-core">click here</a>.

## MANDATORY
> During the evaluation, I was asked questions about the topics below;
- [x] Choose between two Linux-based operating systems: `Rocky` or `Debian`;
- [x] Create at least 2 encrypted partitions using `LVM`;
- [x] Ensure `SSH services` are running on specific ports;
- [x] Configure a `UFW firewall` and leave only port `4242` open;
- [x] Set up the `hostname` (will be changed during evaluation) and a strong `password policy` for all users;
- [x] Set up a strong `sudo` configuration;
- [x] Create a `monitoring script` that displays specific information every 10 minutes at server startup;

## BONUS
> During the evaluation, also had to justify my choices;
- [x] Set up a different partition structure;
- [x] Set up a functional `WordPress` website with the following services: `lighttpd`, `MariaDB` and `PHP`;
- [x] Set up a service of my own choice that I think is useful (justify that choice);

## MONITORING SCRIPT
> `monitoring.sh` broadcasts the machine's state to every open terminal with
> `wall`, every ten minutes, driven by a cron entry.

| Reported | Source |
| :- | :- |
| Architecture and kernel | `uname -m`, `uname -r` |
| Physical processors | Distinct `physical id` entries in `/proc/cpuinfo` |
| Virtual processors | `^processor` lines in `/proc/cpuinfo` |
| RAM available and used | `/proc/meminfo`, `free` |
| Disk available and used | `df -h` on `/` |
| Processor load | `top -bn2` |
| Last reboot | `uptime -s` |
| LVM active | `systemctl is-active lvm2-lvmetad` |
| Active connections | `ss -s` |
| Users logged in | `who` |
| IPv4 and MAC | `ip addr`, `ip link` |
| sudo commands run | `/var/log/auth.log` |

Check it before relying on it:

```bash
bash -n born2beroot/monitoring.sh   # syntax only, runs nothing
bash born2beroot/monitoring.sh      # needs a terminal to write to
```

`shellcheck born2beroot/monitoring.sh` - Catches quoting and portability
problems the shell itself will not complain about.

* [ShellCheck](https://www.shellcheck.net/) - Shell script static analysis. `Website`
* [Debian Handbook](https://debian-handbook.info/) - Administration reference. `Website`

## CONTRIBUTING

This repository documents work already submitted and graded, so it is not open
to changes. Feel free to fork it if any of it is useful to you.

## LICENSE

This project is available under the MIT License. For further details, please refer to the [LICENSE](https://github.com/jotavare/born2beroot/blob/main/LICENSE) file.
