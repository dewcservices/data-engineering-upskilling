# Accessing virtual machines with SSH

## Linux virtual machine

When working in Defence, we typically use Windows computers. While these
computers are fine for common Microsoft applications, they are not usually
suitable for software development. We typically prefer developing using
Linux-based operating systems. However, you are unlikely to work directly on
physical Linux computers when working in Defence. Instead, you are much more
likely to work on a remote virtual Linux machine.

The first step on your software development journey is to create a Linux virtual
machine.

TODO: Add instructions to get a virtual machine on Azure.

## VSCode

When writing software, you can use any text editor or development environment.
However, since you are just getting started, we recommend you use
[Visual Studio Code](https://code.visualstudio.com/) (usually referred to a
VSCode). VSCode is widely available and is easy to install. If it is not already
on your DEWC machine, raise an ICT request to get it installed.

VSCode has builtin support for SSH, which is a protocol that we can use to
access our new virtual machine. You will need to install the SSH extension by
visiting
[here](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh).

Once the SSH extension is installed, you can try accessing your virtual machine.
Type `Ctrl+Shift+P` to bring up the VSCode command palette. Start typing:
`Remote-SSH: Connect to Host`. As you type, you should see this option appear
automatically. Select this option with your arrow keys and click `Enter`. You
will be prompted for the virtual machine address. Type in the virtual machine
address and click `Enter`. You will then be prompted for your password. Once you
have entered your password, click `Enter`.

Upon clicking `Enter`, VSCode will create a new window. This new window is
configured to give the impression that you are "inside" of your virtual machine.
We can check this by doing the following. First, open up the terminal. The
shortcut for opening the terminal in VSCode is `` Ctrl+` ``.

In this terminal, type

```
lsb_release -i
```

and click `Enter`. If this prints `Distributor ID: Ubuntu`, then you have
succesfully remoted into your Linux machine. We specifically use a Linux
distribution called Ubuntu, which is the most widely used Linux distribution.

Close the SSH session, by again opening the command paletter (via
`Ctrl+Shift+P`) and searching for `Remote: Close Remote Connection`.

### SSH Keys

You will SSH into virtual machines a lot during your career. You can save time
on entering your password by generating a pair of so-called SSH keys. To
generate a pair of SSH keys, open your terminal in VSCode (using `` Ctrl+` ``)
and type

```
ssh-keygen
```

Ensure this is done on your _Windows_ machine, not your virtual machine.

Follow the instructions from `ssh-keygen`. Accept the defaults by clicking
`Enter` throughout. At the end of the process, it should generate two files:

- `id_rsa`: This is your private key. Keep this secret and do not distribute
  with anyone.
- `id_rsa.pub`: This is your public key. This can be shared with anyone.

We will copy the public key to our Linux machine. This will allow us to SSH in
the future without needing a password.

View the public key using:

```
cat ~/.ssh/id_rsa.pub
```

Copy this key to your clipboard. This can be fiddly in the terminal. You may
need to "right click" and copy the contents instead of using `Ctrl+C`. You can
also try `Ctrl+Shift+C`.

Follow the previous instructions to remote back into your virtual machine. You
will still need to type your password in - hopefully for the last time!

Create a new file using `Ctrl+N`. Paste the contents of `id_rsa.pub` into the
new file. Then, save the file using `Ctrl+S`. You will be prompted for a place
to save the file. Type in `~/.ssh/authorized_keys` as the save location.

If all has gone to plan, you can close your current session. Upon reopening the
session, you should not need your password any longer. Again, check that you
have successfully remoted into the machine by opening the terminal and typing:

```
lsb_release -i
```

which should print `Distributor ID: Ubuntu`.

## Conclusion

In this section, you:

- Created a Linux virtual machine.
- Accessed the machine via SSH using VSCode.
- Copied over a public key so that you can access the machine without typing in
  your password.

Next, we will learn more about Linux and the terminal.
