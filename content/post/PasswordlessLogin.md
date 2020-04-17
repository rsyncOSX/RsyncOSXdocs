---
layout: post
title:  "Passwordless logins by ssh-keys"
permalink: PasswordlessLogin
---

To enable passwordless login by using ssh you must use `ssh-keygen` to create a private and public key-pair. The method below is a manually setup. [RsyncOSX does also assist in setting up ssh-keys.](/ssh)

## Step by step procedure

If the server is set up listening for ssh on other ports than standard port 22 use `ssh -p port` to use another port. In RsyncOSX there is in parameters setting possible to set another ssh port if required. The `Mac$` is a abbreviation for the terminal prompt.

**Step 1** : create a ssh-keypair on your Mac (from the terminal window) and just press Enter every time `ssh-keygen` ask for input (three times).

`Mac$ ssh-­keygen -­t rsa`

See _comment on ssh-keygen_ below (about RSA or DSA based crypto).

**Step 2** : login to your server and create a `.ssh` directory in your home catalog. The instructions are **four commands**, first `login`, then `cd` then `mkdir` and last `exit`.

`Mac$ ssh user@server.com` `cd` `mkdir .ssh` `exit`

**Step 3** : copy through ssh the public key from the Mac `.ssh` directory to the server.

`Mac$ cat ~/.ssh/id_rsa.pub | ssh user@server.com "cat > .ssh/authorized_keys"`

or use secure copy

`Mac$ scp ~/.ssh/id_rsa.pub user@server.com:.ssh/authorized_keys`

**Step 4** : login in to `user@server.com` and set the correct permissions for the `.ssh` catalog and `authorized_keys` file.

* (1) `ssh user@server.com`
* (2) `cd`
* (3) `chmod 700 .ssh`
* (4) `chmod 600 .ssh/authorized_keys`
* (5) `exit`

**Step 5** : test login from Mac, password is not required.

`Mac$ ssh user@server.com`

If you have two or more servers repeat **step 2 - step 5**. If you have two Macbooks and two servers (which I have) repeat step1 - step 5 for the second MacBook as well.

### Comment on ssh-keygen

My knowledge of crypto is very limited. The parameter **-t rsa** creates one key-pair based on <a href="https://en.wikipedia.org/wiki/RSA_(cryptosystem)" target="_blank">RSA</a>. It might be that your server require a key-pair based on <a href="https://en.wikipedia.org/wiki/Digital_Signature_Algorithm" target="_blank">DSA</a>. The following steps creates a key-pair based on DSA (parameter **-t dsa**):

**Step 1**: create a ssh-keypair on your Mac (from the terminal window) and just press Enter every time `ssh-keygen` ask for input (three times).

`Mac$ ssh-­keygen -­t dsa`

**Step 2**: login to your server and create a `.ssh` directory in your home catalog. The instructions are **four commands**, first `login`, then `cd` then `mkdir` and `exit`.

`Mac$ ssh user@server.com` `cd` `mkdir .ssh` `exit`

**Step 3** copy through ssh the public key from the Mac `.ssh` directory to the server.

`Mac$ cat ~/.ssh/id_dsa.pub | ssh user@server.com "cat > .ssh/authorized_keys2"`

or use secure copy

`Mac$ scp ~/scp .ssh/id_dsa.pub user@server.com:.ssh/authorized_keys2`

**Step 4**: login in to `user@server.com` and set the correct permissions for the `.ssh` catalog and `authorized_keys2` file.

* (1) `ssh user@server.com`
* (2) `cd`
* (3) `chmod 700 .ssh`
* (4) `chmod 600 .ssh/authorized_keys2`
* (5) `exit`

**Step 5**: test login from Mac, password is not required.

`Mac$ ssh user@server.com`
