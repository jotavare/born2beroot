<p align="center">
  <img src="https://github.com/jotavare/jotavare/blob/main/42/banners/piscine_and_common_core/github_piscine_and_common_core_banner_born2beroot.png">
</p>

<p align="center">
	<img src="https://img.shields.io/badge/evaluated-21%20%2F%2012%20%2F%202022-success?color=%2312bab9&style=flat-square"/>
	<img src="https://img.shields.io/badge/score-125%20%2F%20100-success?color=%2312bab9&style=flat-square"/>
	<a href='https://www.linkedin.com/in/jotavare' target="_blank"><img alt='Linkedin' src='https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=data:image/svg%2bxml;base64,PHN2ZyByb2xlPSJpbWciIHZpZXdCb3g9IjAgMCAyNCAyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48dGl0bGU+TGlua2VkSW48L3RpdGxlPjxwYXRoIGZpbGw9IndoaXRlIiBkPSJNMjAuNDQ3IDIwLjQ1MmgtMy41NTR2LTUuNTY5YzAtMS4zMjgtLjAyNy0zLjAzNy0xLjg1Mi0zLjAzNy0xLjg1MyAwLTIuMTM2IDEuNDQ1LTIuMTM2IDIuOTM5djUuNjY3SDkuMzUxVjloMy40MTR2MS41NjFoLjA0NmMuNDc3LS45IDEuNjM3LTEuODUgMy4zNy0xLjg1IDMuNjAxIDAgNC4yNjcgMi4zNyA0LjI2NyA1LjQ1NXY2LjI4NnpNNS4zMzcgNy40MzNjLTEuMTQ0IDAtMi4wNjMtLjkyNi0yLjA2My0yLjA2NSAwLTEuMTM4LjkyLTIuMDYzIDIuMDYzLTIuMDYzIDEuMTQgMCAyLjA2NC45MjUgMi4wNjQgMi4wNjMgMCAxLjEzOS0uOTI1IDIuMDY1LTIuMDY0IDIuMDY1em0xLjc4MiAxMy4wMTlIMy41NTVWOWgzLjU2NHYxMS40NTJ6TTIyLjIyNSAwSDEuNzcxQy43OTIgMCAwIC43NzQgMCAxLjcyOXYyMC41NDJDMCAyMy4yMjcuNzkyIDI0IDEuNzcxIDI0aDIwLjQ1MUMyMy4yIDI0IDI0IDIzLjIyNyAyNCAyMi4yNzFWMS43MjlDMjQgLjc3NCAyMy4yIDAgMjIuMjIyIDBoLjAwM3oiLz48L3N2Zz4K&logoColor=white'/></a>
	<a href='https://profile.intra.42.fr/users/jotavare' target="_blank"><img alt='42' src='https://img.shields.io/badge/Porto-100000?style=flat-square&logo=42&logoColor=white&labelColor=000000&color=000000'/></a>
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
| LVM active | Active logical volumes via `lvs` |
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
