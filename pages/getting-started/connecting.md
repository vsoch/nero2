---
title: Connecting to Nero Cluster
keywords: connecting
summary: "More details on how to connect to Nero Cluster"
sidebar: getting-started_sidebar
permalink: connecting.html
folder: getting-started
---
# Connecting <small>to Nero </small>

!!! warning "Nero account required"

    To be able to connect to Nero, you must first obtain a [Nero
    account][url_account].


## Credentials

All users must have a [Stanford SUNet ID][url_sunet] and a [Nero
account][url_account] to log in to Nero. Your Nero account uses the
same username/password as your SUnet ID:

    Username: SUNet ID
    Password: SUNet ID password

To request a Nero account, please see the [Getting Started][url_account]
page.

!!! important "Resetting passwords"

    Nero does **not** store your SUNet ID password. As a consequence, we
    are unable to reset your password. If you require password assistance,
    please see the [SUNet Account page][url_suaccounts].

## Connection

You MUST be connected to the Stanford VPN to connect to the system; information about
setting up the VPN is available at https://vpn.stanford.edu

Access to Nero is provided via Secure Shell (SSH) login. Most Unix-like
operating systems provide an SSH client by default that can be accessed by
typing the `ssh` command in a terminal window.

To login to Nero, open a terminal and type the following command, where
`<sunetid>` should be replaced by your *actual* SUNet ID:

```bash
$ ssh <sunetid>@nero-login.stanford.edu
```

Upon logging in, you will be connected to one of Nero's load-balanced login
node. You should be automatically directed to the least-loaded login node at
the moment of your connection, which should give you the best possible
environment to work.

--8<--- "_host_keys.md"


### Authentication

#### Password

To ease access and increase compatibility[^krb_legacy] with different
platforms, Nero allows a simple password-based authentication mechanism for
SSH.[^auth_methods].

Upon connection, you will be asked for your SUNet ID password with the
following prompt:

    <sunetid>@nero-login.stanford.edu's password:

Enter your password, and if it's correct, you should see the following line:

    Authenticated with partial success.


#### Second factor (2FA)

Nero implements Stanford's [Minimum Security Standards][url_minsec]
policies which mandate two-step authentication to access the cluster.

Two-step authentication protects your personal information and credentials by
combining something only you *know* (your password) with something only you
*have* (your phone, tablet or token). This prevents an attacker who would steal
your password to actually use it to impersonate you. For more details about
two-step authentication at Stanford, please refer to the [University IT
two-step][url_twostep] page.


After successfully entering your password, you'll be prompted for your second
authentication factor with a message like this:

    Duo two-factor login for <sunetid>

    Enter a passcode or select one of the following options:

     1. Duo Push to XXX-XXX-9999
     2. Phone call to XXX-XXX-9999
     3. SMS passcodes to XXX-XXX-9999 (next code starts with: 9)

    Passcode or option (1-3):


!!! tip "Avoiding two-factor prompt on each connection"

    If you routinely open multiple sessions to Nero, having to confirm each
    one of them with a second authentication factor could rapidely become
    cumbersome. To work around this, the OpenSSH client allows multiplexing
    channels and re-using existing authenticated for opening new sessions.
    Please see the [Advanced Connection Options][url_avoid_duo] page for more
    details.

If your second factor is accepted, you'll see the following message:

    Success. Logging you in...

### Authentication failures

!!! danger "Excessive authentication failures"

    Entering an invalid password multiple times will result in a (temporary)
    ban of your IP address.

To prevent brute-force password guessing attacks on Nero login nodes, we
automatically block IP addresses that generate too many authentication failures
in a given time span. This results in a temporary ban of the infringing IP
address, and the impossibility for the user to connect to Nero from that
IP address.

When this happens, your SSH connection attempts will result in the following
error:

    ssh: connect to host nero-login.stanford.edu port 22: Connection refused



## Login

Congratulations! You've successfully connected to Nero. You'll be greeted
by the following *message of the day*:

```
Welcome to 

            ███╗   ██╗███████╗██████╗  ██████╗ 
            ████╗  ██║██╔════╝██╔══██╗██╔═══██╗
            ██╔██╗ ██║█████╗  ██████╔╝██║   ██║
            ██║╚██╗██║██╔══╝  ██╔══██╗██║   ██║
            ██║ ╚████║███████╗██║  ██║╚██████╔╝
            ╚═╝  ╚═══╝╚══════╝╚═╝  ╚═╝ ╚═════╝ 
                                   
 =======================================================================
   System is designed for high risk data; you still must comply with all
            applicable Stanford policies for high risk data.
 =======================================================================
  This system is for authorized users only and users must comply with all
  Stanford computing, network and research policies. All activity may be
  recorded for security and monitoring purposes. For more information, see
  https://doresearch.stanford.edu/policies/research-policy-handbook and
  https://acomp.stanford.edu/about/policy
 =======================================================================
         email srcc-support@stanford.edu for questions/issues/etc
 =======================================================================
```

## Start computing

To start computing, there's still a extra step required, which is requesting
resources to run your application. It's all described in the [next
section][url_submit].

[comment]: #  (link URLs -----------------------------------------------------)

#[url_prereq]:       /docs/getting-started/prerequisites
[url_account]:      /docs/getting-started/index.md#how-to-request-an-account
#[url_avoid_duo]:    /docs/advanced-topics/connection#avoiding-multiple-duo-prompts
#[url_other_auth]:   /docs/advanced-topics/connection#authentication-methods
[url_suaccounts]:   https://accounts.stanford.edu/
[url_sunet]:        https://uit.stanford.edu/service/accounts/sunetids
[url_minsec]:       https://uit.stanford.edu/guide/securitystandards
[url_twostep]:      https://uit.stanford.edu/service/webauth/twostep
#[url_login]:        /docs/overview/glossary/#login-nodes
[url_submit]:       /docs/getting-started/submitting
[url_contact]:      mailto:srcc-support@stanford.edu
#[url_sshfs]:        /docs/user-guide/storage/data-transfer#sshfs
[url_vpn]:          https://uit.stanford.edu/service/vpn

[comment]: #  (footnotes -----------------------------------------------------)

[^krb_legacy]: On Nero 1.0, GSSAPI tokens (based on Kerberos tickets)
were the only allowed authentication method, which could cause some
interoperability with third-party SSH clients.

[^auth_methods]: For other methods of authentication, see the [Advanced
 Connection Options][url_other_auth] page.
{% include links.html %}
