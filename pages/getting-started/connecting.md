---
title: Connecting to Nero Cluster
keywords: connecting
sidebar: home_sidebar
editable: true
permalink: connecting.html
folder: getting-started
---
# Connecting to Nero

## Credentials

All users must have a [Stanford SUNet ID][url_sunet] and a [Nero
account][url_account] to log in to the Nero Onprem Cluster. 
Your Nero account uses the same username/password as your SUnet ID:
  ```
  Username: SUNet ID
  Password: SUNet Password
  ```

To request a Nero account, please see the [Getting Started][url_account]
page.


{% include important.html content="Resetting passwords<br/>
Nero does **not** store your SUNet ID password.  As a consequence, we
    are unable to reset your SUNet password.  If you require password assistance,
    please see the [SUNet Account page][url_suaccounts]." %}
    

## Connection

You MUST be connected to the Stanford VPN to connect to the system; information about
setting up the VPN is available at [Stanford VPN][url_vpn]

Access to Nero is provided via Secure Shell (SSH) login. Most Unix-like
operating systems provide an SSH client by default that can be accessed by
typing the `ssh` command in a terminal window.

To login to Nero, open a terminal and type the following command, where
`<sunetid>` should be replaced by your *actual* SUNet ID:

```bash
$ ssh <sunetid>@nero-login.stanford.edu
```


### Authentication

#### Password

To ease access and increase compatibility with different platforms, 
Nero allows a simple password-based authentication mechanism for SSH.

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


If your second factor is accepted, you'll see the following message:

    Success. Logging you in...

### Authentication failures

{% include warning.html content="Excessive authentication failures<br/> Entering an invalid password multiple times will result in a (temporary) ban of your IP address." %}

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

[url_account]:      /nero2/getting-started.html#how-to-request-an-account
[url_suaccounts]:   https://accounts.stanford.edu/
[url_sunet]:        https://uit.stanford.edu/service/accounts/sunetids
[url_minsec]:       https://uit.stanford.edu/guide/securitystandards
[url_twostep]:      https://uit.stanford.edu/service/webauth/twostep
[url_submit]:       /nero2/submitting.html
[url_contact]:      mailto:srcc-support@stanford.edu
[url_vpn]:          https://uit.stanford.edu/service/vpn




{% include links.html %}
