---
title: Prerequisites
keywords: start
summary: "General overview about the prerequisites to using the Nero Onprem Cluster"
sidebar: home_sidebar
editable: true
permalink: getting-started.html
folder: getting-started
---

## Basics
To start using Nero, you will need:

* an active [SUNet ID][url_sunet]
* a [Nero account][url_request]
* set up Cisco AnyConnect for connecting to [Stanford VPN][url_vpn]
* a [SSH client][url_ssh]
* some familiarity with [Unix/Linux command-line environments][url_unix], and
  notions of [shell scripting][url_bash].

## Active SUNet ID
Most faculty and staff members should have an active SUNet ID and SUNet base level service is sufficient for using Nero.

{% include note.html content="External
   collaborators, or users without a SUNet ID, can be sponsored by a PI and
   get a sponsored SUNet ID at no cost. Please see the [sponsorship
   page][url_sponsor] for more information." %}


## How to request a Nero account

To request an account, the sponsoring Stanford faculty member should email
srcc-support@stanford.edu, specifying the names and SUNet IDs of
his/her research team members needing an account.

Nero is open to the Stanford community as a computing resource to support
departmental or sponsored research, thus a faculty member's explicit consent is
required for account requests.

Nero is a resource to help and support research, and is not suitable for course work, 
class assignments or general-use training sessions.

There is no fee associated with using Nero, and no limit in the amount of
accounts each faculty member can request. We will periodically ensure that all
accounts associated with each PI are still active, and reserve the right to
close any Nero account whose SUNet ID is expired.



## Connect to Stanford VPN
You MUST be connected to the Stanford VPN to connect to the Nero onprem system; information about
utilizing the Stanford VPN  and configuring Cisco AnyConnect is available at [Stanford VPN Info][url_vpn]


## SSH clients


### Linux

Linux distributions usually come with a version of the [OpenSSH][url_openssh]
client already installed. So no additional software installation is required.
If not, please refer to your distribution's documentation to install it.

### MacOS

MacOS systems usually come with a version of the [OpenSSH][url_openssh] client
already installed. So no additional software installation is required


### Windows

Microsoft Windows doesn't provide any SSH client by default. To install one,
you have several options, depending on the version of Windows.

* **WSL <small>recommended</small>**

    Windows 10 provides a feature called the ["Windows
    Subsystem for Linux"][url_wsl] (WSL). Please refer to the [official
    documentation][url_wsl_doc] or [this howto][url_wsl_howto] for installation
    instructions. Once installed, you'll be able to use the `ssh` command from a
    Windows terminal to connect to Nero.

* Cygwin

    The [Cygwin project][url_cygwin] predates WSL and provides similar features,
    which among other things, allow users to install a command-line SSH client on
    their Windows machines.

The two options above will ensure the best compatibility with the Nero
environment. If you'd like to explore other avenues, many [other SSH client
implementations][url_ssh_clients] are available, but have not necessarily been tested
with Nero, so your mileage may vary.


## Unix/Linux resources

A full tutorial on using Unix/Linux is beyond the scope of this documentation.
However, there are many tutorials for beginning to use Unix/Linux on the web.

A few tutorials we recommend are:

* [Unix Tutorial for Beginners][url_tuto_1] (University of Surrey, UK)
* [Introduction to Unix][url_tuto_2] (Imperial College, London)
* [The Unix Shell][url_tuto_3] (Software Carpentry)

More specifically about HPC:

* [Intro to HPC][url_tuto_5] (HPC Carpentry)
* [HPC in a day][url_tuto_4] (Software Carpentry}


### Text editors

Multiple text editors are available on Nero. For beginners, we recommend
the use of `nano`. And for more advanced uses, you'll also find below some
resources about using `vim`

* [Nano guide][url_nano] (Gentoo wiki)
* [Vim guide][url_vim] (Gentoo wiki)


### Shell scripting

Compute jobs launched on Nero are most often initialized by user-written
shell scripts. Beyond that, many common operations can be simplified and
automated using shell scripts.

For an introduction to shell scripting, you can refer to:

* [Bash Programming - Introduction HOWTO][url_scripting]


[comment]: #  (link URLs -----------------------------------------------------)

[url_sunet]:        https://uit.stanford.edu/service/accounts/sunetids
[url_level]:        https://uit.stanford.edu/service/accounts/sunetids#services
[url_sponsor]:      https://uit.stanford.edu/service/sponsorship/
[url_vpn]:          https://vpn.stanford.edu

[url_openssh]:      https://www.openssh.com/
[url_wsl]:          https://en.wikipedia.org/wiki/Windows_Subsystem_for_Linux
[url_wsl_doc]:      https://msdn.microsoft.com/commandline/wsl
[url_wsl_howto]:    https://www.howtogeek.com/249966/how-to-install-and-use-the-linux-bash-shell-on-windows-10/
[url_cygwin]:       https://cygwin.com
[url_ssh_clients]:  https://en.wikipedia.org/wiki/Comparison_of_SSH_clients#Platform

[url_request]:      /nero2/getting-started.html#how-to-request-an-account
[url_ssh]:          #ssh-clients
[url_unix]:         #unixlinux-resources
[url_bash]:         #shell-scripting

[url_scripting]:    http://tldp.org/HOWTO/Bash-Prog-Intro-HOWTO.html
[url_tuto_1]:       http://www.ee.surrey.ac.uk/Teaching/Unix/
[url_tuto_2]:       http://www.doc.ic.ac.uk/~wjk/UnixIntro/
[url_tuto_3]:       https://swcarpentry.github.io/shell-novice/
[url_tuto_4]:       https://psteinb.github.io/hpc-in-a-day/
[url_tuto_5]:       https://hpc-carpentry.github.io/hpc-intro/


[url_nano]:         https://wiki.gentoo.org/wiki/Nano/Basics_Guide
[url_vim]:          https://wiki.gentoo.org/wiki/Vim/Guide

{% include links.html %}
